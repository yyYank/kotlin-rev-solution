
## リストの前からいくつかを取り除いた部分リストを切り出す

drop関数を使います

### フォーマット

    drop(削る要素数)

### 実装サンプル

    val array = arrayOf(1, 2, 3, 4, 5)
    array.drop(1).forEach{println(it)} // => 2, 3, 4, 5
    array.drop(2).forEach{println(it)} // => 3, 4, 5
    array.drop(3).forEach{println(it)} // => 4, 5
    array.drop(4).forEach{println(it)} // => 5
    array.drop(5).forEach{println(it)} // => 空のArray


### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin /drop](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/drop.html)
