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



### 関数オブジェクト
   
   
   
KotlinではJavaScriptなどのように関数オブジェクトを宣言できます。
例えば、先ほどのgreetTo関数を以下のように書き換え可能です。

    val greetTo  = {
        (person : String) -> "hello! $person"
    }
    println(greetTo("duke"))
    
またはこんな感じです。  
   
   

    val greetMessage  = {
        (person : String) -> "hello! $person"
    }("duke")
    println(greetMessage)
    
   
   
   
簡単にフォーマットを示すとこんな感じです。

    {
        (引数 : 型) -> 処理
    }



<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
