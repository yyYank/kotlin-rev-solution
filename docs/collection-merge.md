
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
            Person("kimura", birthDayToAge(LocalDate.of(1972,11,13))),
            Person("kusanagi", birthDayToAge(LocalDate.of(1974,7,9))),
            Person("katori", birthDayToAge(LocalDate.of(1977,1,31))),
            Person("inagaki", birthDayToAge(LocalDate.of(1973,12,8))),
            Person("nakai", birthDayToAge(LocalDate.of(1972,8,18)))
        )
    
        // なんでも作るグループ
        val tGroup = arrayOf(
            Person("nagase", birthDayToAge(LocalDate.of(1978,11,7))),
            Person("joushima", birthDayToAge(LocalDate.of(1970,11,17))),
            Person("matsuoka", birthDayToAge(LocalDate.of(1977,1,11))),
            Person("yamaguchi", birthDayToAge(LocalDate.of(1972,1,10))),
            Person("kokubun", birthDayToAge(LocalDate.of(1974,9,2)))
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
    
    fun birthDayToAge(birthday : LocalDate) = ChronoUnit.YEARS.between(birthday, LocalDate.now())

### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin / merge](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/merge.html)


