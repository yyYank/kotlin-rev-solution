
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


https://kotlinlang.org/docs/reference/data-classes.html



### object

シングルトンなオブジェクトとか作りたいときに使う。

https://kotlinlang.org/docs/reference/object-declarations.html


## inline

関数をインライン化することが出来、毎回インスタンス生成するようなオーバーヘッドを避けられる。
inline関数内の特定の箇所をinline化したくない場合はnoinlineを使うようだ。

https://kotlinlang.org/docs/reference/inline-functions.html




## infix
## tailrec

末尾再起最適化をするためのキーワード。


## companion


## is

型チェックなどで使われる。Javaでいうinstanceofが近い。

## in



## out


## vararg

引数を可変長としたいときに使う

## as
## by
## to
## reified
## let
## lateinit
