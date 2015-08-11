#既存のクラスに機能を追加する

KotlinではC#のように既存クラスのソースに変更を行うことなく、機能を追加することができます。

##拡張関数

既存のクラスに関数を追加するには、以下のように書きます。

    fun MyClass.isEmpty() : Boolean {
      return this.A == null // thisはMyClassのオブジェクトを参照します
    }

##拡張プロパティ

既存のクラスにプロパティを追加するには、以下のように書きます。

    val MyClass.B : String
      get() = A?.toString()

    var MyClass.C : String? = null


####参考

[Kotlin Reference - Extensions](http://kotlinlang.org/docs/reference/extensions.html)

#### ページ公開時のKotlinのバージョン
   
0.12.613
