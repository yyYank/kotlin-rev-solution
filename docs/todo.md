
# TODOタスクをソースに残す


Kotlinの場合TODO関数が用意されており、実行時にエラーにしてくれたります。
もちろんJavaと同様にコメントとしてTODOを残すことも可能です。


関数の定義

    inline fun TODO(): Nothing (source)
    inline fun TODO(reason: String): Nothing (source)
    
使い方

    TODO()
    TODO("hogehogeなためfugafugaする")
    
