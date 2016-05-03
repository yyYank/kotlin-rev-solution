

# Kotlinのコレクション・フレームワークを知りたい


Javaにコレクションフレームワークがあるように、Kotlinにもコレクションフレームワークがある。
Kotlinのコレクションフレームワークはread onlyなコレクションとmutableなコレクションで構成されている。


# Collection

kotlin.collection.Collectionインターフェース。

    interface Collection<out E> : Iterable<E>

EはCollectionの要素。このインターフェースはread only 飲みサポートする。 read/writeアクセスはMutableCollection インターフェースがサポートする。


# MutableCollection
## List
## MutableList

## Map
## MutableMap

## Set
## MutableSet
