## 関数を宣言する

関数の宣言はfunを使います。   
関数はクラスに属す必要はありません。トップレベルに定義できます。   
(クラスの関数としても宣言できます)


### フォーマット
   
   
   
   
    fun 関数名(仮引数 : 型) : 型 = 処理
    fun 関数名(仮引数 : 型) : 型 {
        処理
    }
   
   
   
### 実装サンプル


以下のように実装できます。

   
   
   
    fun greetPerson() : String = "yank"
    
    fun greet() : Unit {
      println("hello")
    }

    fun greetTo(person : String) : Unit = println("hello! $person")


さらに推論される型は省略できます。

    fun greetPerson() = "yank"
    
    fun greet() {
      println("hello")
    }

    fun greetTo(person : String) = println("hello! $person")

   
   
   
$personは文字列への埋め込みの記法です。




<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
