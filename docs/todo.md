
# TODOタスクをソースに残す


Kotlinの場合TODO関数が用意されており、実行時にエラーにしてくれたります。
もちろんJavaと同様にコメントとしてTODOを残すことも可能です。


関数の定義

    inline fun TODO(): Nothing (source)
    inline fun TODO(reason: String): Nothing (source)
    
使い方

    TODO()
    TODO("hogehogeなためfugafugaする")
    
    
こうすると実行時に例外が投げられます。

    Exception in thread "main" kotlin.NotImplementedError: An operation is not implemented: hogehogeなためfugafugaする
        at sample.Simplest_versionKt.main(Simplest version.kt:11)
    
[https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-t-o-d-o.html](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-t-o-d-o.html)
