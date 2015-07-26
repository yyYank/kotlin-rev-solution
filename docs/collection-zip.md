## ２つのリストのペアのリストを作る

zip関数を使います

### フォーマット

### 実装サンプル


分かりやすく、2つのグループで2人1組になってもらいます。

    // 年齢と名前を持ったクラス
    class Person(name : String, age : Int) {
        val name = name
        val age = age
    }

    fun main (args : Array<String>) {    
        // なんでもこなすグループ
        val sGroup = arrayOf(
            Person("kimura", 42), // 1972/11/13
            Person("kusanagi", 41), // 1974/7/9
            Person("katori", 37), // 1977/1/31
            Person("inagaki", 41), // 1973/12/8
            Person("nakai", 42) // 1972/8/18
        )

        // なんでも作るグループ
        val tGroup = arrayOf(
            Person("nagase", 36), // 1978/11/7
            Person("joushima", 44), // 1970/11/17
            Person("matsuoka", 38), // 1977/1/11
            Person("yamaguchi", 43), // 1972/1/10
            Person("kokubun", 40) // 1974/9/2
        )
    
        // 2グループのそれぞれの人の名前を出力
        sGroup.zip(tGroup).forEach{println(
            it.first.name + "と" + it.second.name
        )}
    
        // 一般的にはこういう書き方をします
        sGroup.zip(tGroup).forEach{println(
            "${it.first.name}と${it.second.name}"
        )}
    }


出力結果

    kimuraとnagase
    kusanagiとjoushima
    katoriとmatsuoka
    inagakiとyamaguchi
    nakaiとkokubun



### 参考URL


[Kotlin公式ドキュメント stdlib / kotlin / zip](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/zip.html)
