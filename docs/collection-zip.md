## ２つのリストのペアのリストを作る

zip関数を使います

### フォーマット

### 実装サンプル


分かりやすく、2つのグループで2人1組になってもらいます。

    // 年齢と名前を持ったクラス
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
    
        // 2グループのそれぞれの人の名前を出力
        sGroup.zip(tGroup).forEach{println(
            it.first.name + "と" + it.second.name
        )}
    
        // 一般的にはこういう書き方をします
        sGroup.zip(tGroup).forEach{println(
            "${it.first.name}と${it.second.name}"
        )}
    }
    
    fun birthDayToAge(birthday : LocalDate) = ChronoUnit.YEARS.between(birthday, LocalDate.now())


出力結果

    kimuraとnagase
    kusanagiとjoushima
    katoriとmatsuoka
    inagakiとyamaguchi
    nakaiとkokubun



### 参考URL


[Kotlin公式ドキュメント stdlib / kotlin / zip](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/zip.html)

