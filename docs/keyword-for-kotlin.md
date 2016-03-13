
# Kotlinのキーワードを知りたい

KotlinではJavaとのcompatibilityを目的にしたものはアノテーション、Kotlin側で使われるものをキーワードと表現する傾向があります。

キーワードには以下のようなものがあります。

## public

キーワードというかアクセス修飾子。
Javaとほぼ同じ。Kotlinではデフォルトのアクセスレベルがpublicとなっている。

## private

キーワードというかアクセス修飾子。
Javaとほぼ同じ。


## open

classの継承をする際に親クラスにつける。
Kotlinではデフォルトで継承不可なクラスとなっている。

    open class Hoge

## inline

関数をインライン化することが出来、毎回インスタンス生成するようなオーバーヘッドを避けられる。
inline関数内の特定の箇所をinline化したくない場合はnoinlineを使うようだ。

https://kotlinlang.org/docs/reference/inline-functions.html

## internal
## infix
## tailrec

末尾再起最適化をするためのキーワード。


## data

toString、hashCode,equalsなどの基本的な関数を定義したクラスを使いたいときに用いる。data classをつくる時のmodifier


https://kotlinlang.org/docs/reference/data-classes.html

## is
## companion
## object
## in
## out
## vararg
## as
## by
## to
## reified
## let
## lateinit
