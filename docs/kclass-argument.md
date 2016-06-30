
# クラスを引数にとる関数をつくる


引数としてクラスを関数に渡したい場合は以下のように書きます。

    fun  <T : Any> jsonToObject(jsonString : String, clazz : KClass<T>) {
        // 処理
    }


Kotlinのクラスは"KClass<T:Any>"です。  
この関数を使う側は以下のように書きます。


    jsonToObject(jsonString, Hoge::class)

