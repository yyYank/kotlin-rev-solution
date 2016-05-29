#既存のクラスに機能を追加する

KotlinではC#のように既存クラスのソースに変更を行うことなく、機能を追加することができます。

##拡張関数

既存のクラスに関数を追加するには、以下のように書きます。

    class User(var name = "")

    // Userクラスに関数を追加
    fun User.isEmptyName() = this.name == "" // thisはUserのオブジェクトを参照します

##拡張プロパティ

既存のクラスにプロパティを追加するには、以下のように書きます。

    // さん付けの名前プロパティを持たせる
    val User.appendedName : String
        get() = name.toString() + "さん"

拡張プロパティで注意しなければならないのは、実際にクラスにはメンバーを挿入していない点です。
バッキングフィールドを持てないため、初期化子を利用することは許可されていません。
getter/setterでのみ値の決定が可能です。



####参考

[Kotlin Reference - Extensions](http://kotlinlang.org/docs/reference/extensions.html)

#### ページ公開時のKotlinのバージョン
   
0.12.613
