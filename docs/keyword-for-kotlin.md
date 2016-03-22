
# Kotlinのキーワードを知りたい

KotlinではJavaとのcompatibilityを目的にしたものはアノテーション、Kotlin側で使われるものをキーワードと表現する傾向があります。

キーワードには以下のようなものがあります。

## Visibility Modifier

キーワードというかアクセス修飾子。


https://kotlinlang.org/docs/reference/visibility-modifiers.html

### public

Javaとほぼ同じ。Kotlinではデフォルトのアクセスレベルがpublicとなっている。

### private

Javaとほぼ同じ。クラス内からのみアクセス可能。


### protected

Javaとほぼ同じ。同一クラスかサブクラスからアクセス可能。


### internal

同一モジュール内ならどこでも見える。



## classのキーワード

### open

classの継承をする際に親クラスにつける。
Kotlinではデフォルトで継承不可なクラスとなっている。

    open class Hoge

### data

toString、hashCode,equalsなどの基本的な関数を定義したクラスを使いたいときに用いる。data classをつくる時のmodifier

    data class Hoge(val fuga : String)


https://kotlinlang.org/docs/reference/data-classes.html



### object

シングルトンなオブジェクトとか作りたいときに使う。

https://kotlinlang.org/docs/reference/object-declarations.html


## 関数につけるキーワード

### inline

関数をインライン化することが出来、毎回インスタンス生成するようなオーバーヘッドを避けられる。
inline関数内の特定の箇所をinline化したくない場合はnoinlineを使うようだ。

https://kotlinlang.org/docs/reference/inline-functions.html




### infix

infixを関数に付与することで中置記法が出来る。

https://kotlinlang.org/docs/reference/functions.html


### tailrec

末尾再起最適化をするためのキーワード。
これでスタックオーバーフローとかしないようになるので安心。

    tailrec fun findFixPoint(x: Double = 1.0): Double
        = if (x == Math.cos(x)) x else findFixPoint(Math.cos(x))

## companion

staticな関数とかを使いときに使う。companion object。

    class MyClass {
      companion object Factory {
        fun create(): MyClass = MyClass()
      }
    }
    
    
    val instance = MyClass.create()
    
    

https://kotlinlang.org/docs/reference/object-declarations.html

## is

型チェックなどで使われる。Javaでいうinstanceofが近い。

## in

ジェネリクスで入力のみ可能なコレクションクラスの宣言とかに使う。型パラメータを反変(contravariant)にする。

## out

ジェネリクスで出力のみ可能なコレクションクラスの宣言とかに使う。

## vararg

引数を可変長としたいときに使う

## as

別名をつける場合、キャストする場合に利用する。

## by

フィールドのデリゲーションで使う。

    class Example {
      var p: String by Delegate()
    }
    
The syntax is: val/var <property name>: <Type> by <expression>.

## to


## reified

読み方はカタカナで書くならリーアファイドとかレイアファイドとか。
javaのクラス指定を少し簡略化してような代物。

    inline fun <reified T> membersOf() = T::class.members


    fun main(s: Array<String>) {
        println(membersOf<StringBuilder>().joinToString("\n"))
        // こう書かなくて良い println(membersOf<StringBuilder::class.java>().joinToString("\n"))
    }
    
    
たろうさんの記事が詳しい。(M10と現在だとややjavaClass<T>とかあたりは変わっている)
http://taro.hatenablog.jp/entry/2015/01/29/223239

https://kotlinlang.org/docs/reference/inline-functions.html#reified-type-parameters


## let,with,run,apply

スコープ関数と言われる便利なやつ

http://qiita.com/ngsw_taro/items/d29e3080d9fc8a38691e


## lateinit

主に@Injectや@AutowiredなどのDIでフィールドインジェクションをしたい場合に
フィールドにつける。あとはJUnitの@SetUpなど。
変数はvarにしておかないとダメなのがちょっとやだ。

    lateinit var subject: TestSubject
