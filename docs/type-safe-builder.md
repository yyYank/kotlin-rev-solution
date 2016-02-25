
# 親子関係のある独自のブロックを作りたい

Groovy風のType-Safe buildersを作りましょう。


[Type-Safe Builders](https://kotlinlang.org/docs/reference/type-safe-builders.html)


### 関数を引数に渡すと出来そう

単純にブロックだけを作ろうとするとこういう関数を定義することになります。

    
    fun parent(f: () -> Unit){}
    fun child (f:() -> Unit){}
    



### 問題点

この関数には親子関係がないので、こう書けてしまいます。


    parent{
        println("おや")
    }

    child {
        println("こども")
    }
    
    
### 親子関係をType-Safe Buildersで表現

これも防ぎたい、あとうまく親子関係で情報を受け渡したい場合に
Type-Safe Buildersです。


    fun parent(init: Parent.() -> Unit) : Parent{
        val parent = Parent()
        parent.init()
        return parent
    }

    class Parent(){
        fun child(init: Child.() -> Unit) : Child {
            val child = Child()
            child.init()
            return child
        }
    }
    
    class Child


## 使い方



さっきのがコンパイルエラーになります


    parent{
        println("おや")
    }

    child { // コンパイルエラー!!
        println("こども")
    }
    

## 解説


Type-Safe Buildersのポイントはレシーバーです。

「クラス名().->」と書くことで、当該クラスをレシーバーとしてそのクラスインスタンスに従属する引数なしの関数という定義になります。    

これを組み合わせると前述のようにクラスでうまく隠蔽や情報の伝達が可能になります。



