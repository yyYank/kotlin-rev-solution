
## リストの要素を前からいくつか取り出す

take関数を使います

### フォーマット

    take(取り出す要素数)

### 実装サンプル

    val array = arrayOf(1, 2, 3, 4, 5)
    array.take(1).forEach { println(it) } // => 1
    array.take(2).forEach { println(it) } // => 1, 2
    array.take(3).forEach { println(it) } // => 1, 2, 3
    array.take(4).forEach { println(it) } // => 1, 2, 3, 4
    array.take(5).forEach { println(it) } // => 1, 2, 3, 4, 5


### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin /take](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/take.html)
