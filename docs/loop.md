## ループ処理を行う

ループ処理にはいくつかの構文があります。   
   
* for
* do-while
* while

### for


フォーマットは以下のとおりです。


    for(任意の変数名 in イテレータブルなオブジェクト) {
        処理
    }

   
   
実際には以下のように書きます。
   
    val arr = listOf(1, 2, 3, 4, 5)
    for (value in arr) {
        print(value) // 1 2 3 4 5
    }


### イテレータブルなオブジェクト
   
   
イテレータブルというと難しそうですが、配列などをイメージしてもらえれば大体あっています。   
以下のような性質を持つものの事を言います。    

* 関数 iterator()を持っている（クラスがjava.lang.Iterableを実装している必要はない）
* 関数 next()を持っている、かつ、Boolean型の関数 next() またはプロパティnext を持っている


### for(int i = 0; i < 10; i++)とかをするには
   
   
Javaのように条件式を書くことはできませんが、
Range構文を使用して値の取りうる範囲と、ステップを指定する事ができます。

以下のように書きます。

    for (i in 0..4) print(i) // "01234"

    for (i in 0..4 step 2) print(i) // "024"

    for (i in 4 downTo 0) print(i) // "43210"

    for (i in 4 downTo 0 step 2) print(i) // "420"

    for (x in 1.0..2.0) print("$x ") // "1.0 2.0 "
   
    for (x in 1.0..2.0 step 0.3) print("$x ") // "1.0 1.3 1.6 1.9 "

    for (x in 2.0 downTo 1.0 step 0.3) print("$x ") // "2.0 1.7 1.4 1.1 "
   
   
### 参考

[プログラミング言語Kotlin-3.4 制御構文](https://sites.google.com/site/tarokotlin/3-kotlinno-biao-zhunapi/sec34)

[Kotlin Reference - Ranges](http://kotlinlang.org/docs/reference/ranges.html)

   
   
whileとdo-whileに関しては他の言語とほぼ同じです。


### while

   
フォーマットは以下のとおりです。   
   
   

    while(条件){処理}
   
   
   
実装サンプルは以下のとおりです。   
   
   
    var i = 0
    while (i < 10) {
        print(i++) // 0 1 2 3 4 5 6 7 8 9
    }
### do-while
   
   

   
フォーマットは以下のとおりです。   
   
   
    do{処理}while(条件)
   
   
実装サンプルは以下のとおりです。   
   
   
   
   
    var i = 0
    do {
        print(i++) // 0 1 2 3 4 5 6 7 8 9
    } while(i < 10)
   
   
   
   
   
  
