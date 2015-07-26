## リストの要素をループして操作する

forEach関数を使います

### フォーマット

    forEach{ 処理 }

### 実装サンプル

    val array = arrayOf(1, 2, 3, 4, 5)
    
    // ラムダを使った書き方
    array.forEach({ element ->
        println(element) 
    }) // => 1,2,3,4,5
    
    // （）は省略できます
    array.forEach{ element ->
        println(element) 
    } // => 1,2,3,4,5
    
    // itでラムダの変わりに要素を評価することも可能
    array.forEach{
        println(it) 
    } // => 1,2,3,4,5


### 参考URL
 
[Kotlin公式ドキュメント stdlib / kotlin / for-each](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/for-each.html)   
