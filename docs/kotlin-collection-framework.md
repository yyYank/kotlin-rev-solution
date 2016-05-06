# Kotlinのコレクション・フレームワークを知りたい


Javaにコレクションフレームワークがあるように、Kotlinにもコレクションフレームワークがある。
Kotlinのコレクションフレームワークはread onlyなコレクションとmutableなコレクションで構成されている。


# Collection

kotlin.collection.Collectionインターフェース。

    interface Collection<out E> : Iterable<E>

EはCollectionの要素。このインターフェースはread only のみサポートする。 read/writeアクセスはMutableCollection インターフェースがサポートする。


# MutableCollection

    interface MutableCollection<E> : Collection<E>, MutableIterable<E>

EはCollectionの要素。このインターフェースはread/writeアクセスをサポートする。

## List

Listインターフェース。Collectionインターフェースを継承している。

    interface List<out E> : Collection<E>
    
EはCollectionの要素。このインターフェースはListのread onlyな操作のみ提供する。
read/writeアクセスはMutableListインターフェースが提供する。

## MutableList

MutableなListインターフェース。

    interface MutableList<E> : List<E>, MutableCollection<E>

Eはコレクションの要素。要素の追加・削除の機能を提供するインターフェース。


## Map

    interface Map<K, out V>

## MutableMap

    interface MutableMap<K, V> : Map<K, V>


## Set

A generic unordered collection of elements that does not support duplicate elements. Methods in this interface support only read-only access to the set; read/write access is supported through the MutableSet interface.

    interface Set<out E> : Collection<E>

## MutableSet

    interface MutableSet<E> : Set<E>, MutableCollection<E>

参考URL

[https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/)
