# クラスのメタデータを取得する

リフレクションによって、クラスのメタデータを取得する事ができます。
現状、Kotlin独自のメタデータ(プロパティ等)はKClass、
Javaと共通のメタデータ(関数、コンストラクタ等)はJavaのClassを使用してアクセスします。
(最新SnapShot(2015/8/11時点)では、KClassの操作のみでクラスの全情報にアクセスできるようになりつつあります)

リフレクションによってクラスのメタデータを取得する方法は2種類あります。

### 静的に取得する

クラスの静的情報から取得する場合、以下のように書きます。

    import kotlin.reflect.jvm.java

    class MyClass(){
        val value = "MyClassのバリュー"
        fun add(x : String, y : String) = x + y
    }
    
    val kClass = MyClass::class // Kotlinのクラスインスタンス
    val jClass = kClass.java // Javaのクラスインスタンス
    

### 動的に取得する

動的に生成されるインスタンスから取得する場合、以下のように書きます。

    import kotlin.reflect.jvm.kotlin
    
    val obj = MyClass() // インスタンス生成
    val jClass = obj.javaClass // Javaのクラスインスタンス
    val kClass = jClass.kotlin // Kotlinのクラスインスタンス
    

## プロパティの取得

KClassのメタデータを使用して、対象のオブジェクトのプロパティリストを取得するには、次のように書きます。
    
    import kotlin.reflect.jvm.javaGetter
    
    val obj = MyClass()
    val kClass = MyClass::class
    val properties = kClass.properties
    for(property in properties) {
        println(property.name + ":" + property.javaGetter?.invoke(obj)) // => value:MyClassのバリュー
        //  こうも書ける println("${property.name}:${property.javaGetter?.invoke(obj)}")
    }

この時のpropertiesの型は、Collection<KMemberProperty<T, out Any?>>となっており、
値を取得するだけでなく、設定も行いたい場合はKMutableMemberPropertyにキャストする必要があります。

    import kotlin.reflect.KMutableMemberProperty
    import kotlin.reflect.jvm.javaGetter
    import kotlin.reflect.jvm.javaSetter
    
    val obj = MyClass()
    val kClass = MyClass::class
    val properties = kClass.properties
    
    for(property in properties) {
        // 変更可能なメンバのみ、Setterが取得できる
        val setter = if (property is KMutableMemberProperty){property.javaSetter} else { null }
        // String型の場合にのみセットする
        if (setter?.getParameterTypes()?.get(0)?.isAssignableFrom(String.javaClass) ?: false){
            setter?.invoke(obj, "set")  
        }
    }

そのクラスおよびスーパークラスで定義したプロパティは上記のpropertiesで、
そのクラスおよびスーパークラスに対して定義された拡張プロパティはextensionProperties、
それらのうちスーパークラスに定義されたものを除いたものはそれぞれdeclaredProperties、declaredExtensionPropertiesで
取得することができます。

##メソッドの呼び出し

現状、メソッドやコンストラクタを呼ぶにはJava側の機能を使用する必要があります。


    import kotlin.reflect.jvm.java

    val obj = MyClass()
    val jClass = obj.javaClass
    val method = jClass.getMethod("add", String::class.java, String::class.java)
    val result = method.invoke(obj, "X", "Y")
    println(result) // => XY

Javaでinvokeメソッドを呼ぶ場合のように、コレクションにパラメータを作りこむ場合は、
コレクションをスプレッド演算子(*)を使用して展開する。

    import kotlin.reflect.jvm.java

    val obj = MyClass()
    val jClass = obj.javaClass
    val method = jClass.getMethod("add", String::class.java, String::class.java)
    val params = arrayOf("XX", "YY")
    val result = method.invoke(obj, *params)
    println(result) // => XXYY

