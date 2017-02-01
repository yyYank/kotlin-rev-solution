
# コールバックヘルとサヨナラしたい


coroutinesを使うと良いかもしれません。


## 導入されたversion

1.1(experimental)

1.2で非同期用のAPIが追加されるが、async/awaitの文法上の変更は無いとのこと。


## サンプルコード

```kotlin
future {
    val original = asyncLoadImage("...original...") // creates a Future
    val overlay = asyncLoadImage("...overlay...") // creates a Future
    ...
    // suspend while awaiting the loading of the images
    // then run `applyOverlay(...)` when they are both loaded
    return applyOverlay(original.await(), overlay.await())
}
```


```kotlin
// inferred type is Sequence<Int>
val fibonacci = buildSequence {
    yield(1) // first Fibonacci number
    var cur = 1
    var next = 1
    while (true) {
        yield(next) // next Fibonacci number
        val tmp = cur + next
        cur = next
        next = tmp
    }
}
```


## 環境設定

* コマンドライン： -Xcoroutines=enabled オプションをつける
* Gradle: gradle.properties or local.properties で kotlin.coroutines=enableを設定
* Maven: <configuration> <args> <arg>-Xcoroutines=enable</arg> </args> </configuration> を設定
* IDE: quick-fix (Alt+Enter)かfacet optionsで編集可能(Project Structure -> Modules -> Your Module -> Compiler -> Coroutines (experimental))

## 参考URL

* [https://www.youtube.com/watch?v=4W3ruTWUhpw](https://www.youtube.com/watch?v=4W3ruTWUhpw)
* [https://blog.jetbrains.com/kotlin/2017/01/kotlin-1-1-beta-is-here/](https://blog.jetbrains.com/kotlin/2017/01/kotlin-1-1-beta-is-here/)
* [https://github.com/Kotlin/kotlin-coroutines](https://github.com/Kotlin/kotlin-coroutines)
* [https://github.com/Kotlin/kotlin-coroutines/blob/master/kotlin-coroutines-informal.md](https://github.com/Kotlin/kotlin-coroutines/blob/master/kotlin-coroutines-informal.md)
