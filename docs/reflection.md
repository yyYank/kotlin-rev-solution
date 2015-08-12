#クラスのメタデータを取得する

リフレクションによって、クラスのメタデータを取得する事ができます。
現状、Kotlin独自のメタデータ(プロパティ等)はKClass、
Javaと共通のメタデータ(関数、コンストラクタ等)はJavaのClassを使用してアクセスします。
(最新SnapShot(2015/8/11時点)では、KClassの操作のみでクラスの全情報にアクセスできるようになりつつあります)

リフレクションによってクラスのメタデータを取得する方法は2種類あります。

###静的に取得する

以下のように書きます。

    val kClass = MyClass::class
    val jClass = kClass.java


###動的に取得する

以下のように書きます。

    val jClass = obj.javaClass
    val kClass = jClass.kotlin

##プロパティの取得

KClassのメタデータを使用して、対象のオブジェクトのプロパティリストを取得するには、次のように書きます。

    val properties = kClass.properties
    for(property in properties) {
      println(property.name + ":" + property.javaGetter.invoke(obj))
    }

この時のpropertiesの型は、Collection<KMemberProperty<T, out Any?>>となっており、
値を取得するだけでなく、設定も行いたい場合はKMutableMemberPropertyにキャストする必要があります。

    val properties = kClass.properties
    for(property in properties) {
      println(property.name + ":" + property.javaGetter.invoke(obj))
      // 変更可能でかつString型の場合にのみセットする
      if (property is KMutableMemberProperty 
      && property.javaSetter.getParameterTypes()[0].isAssignableFrom(String::class)) {
        property.javaSetter.invoke(obj, "set")
      }
    }

そのクラスおよびスーパークラスで定義したプロパティは上記のpropertiesで、
そのクラスおよびスーパークラスに対して定義された拡張プロパティはextensionProperties、
それらのうちスーパークラスに定義されたものを除いたものはそれぞれdeclaredProperties、declaredExtensionPropertiesで
取得することができます。

##メソッドの呼び出し

現状、メソッドやコンストラクタを呼ぶにはJava側の機能を使用する必要があります。

    val method = jClass.getMethod("XXX", String::class, String::class)
    val result = method.invoke("XX", "YY")

Javaでinvokeメソッドを呼ぶ場合のように、コレクションにパラメータを作りこむ場合は、
コレクションをスプレッド演算子(*)を使用して展開する。

    val params = toArrayList("XX", "YY")
    val result = method.invoke(*params)

#### ページ公開時のKotlinのバージョン
   
0.12.613
