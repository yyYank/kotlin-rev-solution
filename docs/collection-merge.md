
## リストをマージする

merge関数を使います

### フォーマット

    マージする対象のリストA.merge(マージする対象のリストB){戻り値}

### 実装サンプル

    // 年齢と名前を持つクラス
    class Person(val name : String, val age : Int)

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
    
        // 年齢の高い方をマージする
        kGroup
        .merge(tGroup){
            k,t -> if (k.age > t.age) k else t　// 年上のPersonを選択
        }.forEach{
             println(it.name)
        } // => kimura,joushima,matsuoka,yamaguchi,nakai
        // なかなか見ないキャスティングになった
    }

### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin / merge](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/merge.html)
