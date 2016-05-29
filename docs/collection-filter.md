

## 条件でリストの要素を絞り込む
  
  
filter関数を使います

### フォーマット

    filter { 条件 }

### 実装サンプル

    val array = arrayOf(1, 2, 3, 4, 5) // => 1,2,3,4,5 のArrayの生成
    // filterの中に条件となる関数を渡します
    array.filter({e -> e % 2 == 0}).forEach{ println(it) } // => 2,4
    // （）は省略出来ます
    array.filter{e -> e % 2 == 0}.forEach{ println(it) } // => 2,4
    // ラムダで書かなくてもitで代用することも可能です
    array.filter{it % 2 == 0}.forEach{ println(it) } // => 2,4
    
### 参考URL

[Kotlin公式ドキュメント stdlib / kotlin / filter](http://kotlinlang.org/api/latest/jvm/stdlib/kotlin/filter.html)
