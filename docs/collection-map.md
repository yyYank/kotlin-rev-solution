## リストの要素の名前のみを抽出する

map関数を使います

### フォーマット

    map { 値 }

### 実装サンプル

    // 名前と年齢を持つだけのクラスを定義
    class Person(val name : String, val age : Int)

    fun main (args : Array<String>) {    
        val array = arrayOf(
            Person("kimura", 42), // 1972/11/13
            Person("kusanagi", 41), // 1974/7/9
            Person("katori", 37), // 1977/1/31
            Person("inagaki", 41), // 1973/12/8
            Person("nakai", 42) // 1972/8/18
        ) 
        // lambdaでuserインスタンスを引数とします
        array.map({user -> user.name}).forEach{println(it)} 　// kimura,kusanagi,katori,inagaki,nakai
        // （）は省略できます
        array.map{user -> user.name}.forEach{println(it)}　 // kimura,kusanagi,katori,inagaki,nakai
        // itで代用できます(このitはUserのインスタンス)
        array.map{it.name}.forEach{println(it)}　　// kimura,kusanagi,katori,inagaki,nakai
    }


第一線で活躍する40代


### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin / map](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/map.html)
