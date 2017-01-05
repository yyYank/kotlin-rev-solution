
# type aliasについて

Kotlinのtype aliasはその名の通り、型に対して別名（エイリアス）を付ける機能です。


## version

Kotlin 1.1以降

## 文法

    typealias 任意の型
    
## 書き方

* Function Type

    typealias MyHandler = (Int, String, Any) -> Unit
    typealias HtmlBuilderAction = HtmlBuilder.() -> Unit
    typealias Predicate<T> = (T) -> Boolean
    
* コレクション
    
    typealias NodeSet = Set<Network.Node>
    typealias FilesTable<K> = MutableMap<K, MutableList<File>>

* Nestしたクラス


    class Outer {
      class Nested {
        inner class Inner
      }
    }
    typealias Something = Outer.Nested.Inner

    
## 参考URL

https://github.com/Kotlin/KEEP/blob/master/proposals/type-aliases.md
