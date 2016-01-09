##式として扱う制御構文

Kotlinでのwhen,ifは条件分岐としての役割だけでなく、   
式として評価するための構文でもあります。


###ifを式として扱う

以下のようにifをStringの戻り値を持つ、処理のように扱うことが出来ます。   
（もちろん、IntでもBigDecimalでも問題ありません）
その場合、ifブロック最後のステートメントの評価値である<br/>
『 "期待通り"』が変数『result』に代入されます。

    val hoge = "hoge"
    val result :String = if(hoge == "hoge") { "期待通り" } else { "hogeじゃない"}
    
    println(result) // => 期待通り
    
    
  {}を省略して以下のように書くことも出来ます

        val hoge = "hoge"
        val result:String = 
          if(hoge == "hoge")  "期待通り" 
          else  "hogeじゃない"
        println(result) // => 期待通り
       

[条件分岐を行う](../if-statement)で書いた処理も   
厳密にはUnitという戻り値を持たない処理ための型を返しています。
  
###whenを式として扱う  
以下のようにwhenを式として扱うことも可能です
whenもifと同じように最後のステートメントの評価値をresultに代入し、
この場合、『"Selected kotlin"』が代入されたString型の変数『result』が得られます

    val lang="kotlin"
    val result:String= when (lang) {
        "kotlin" -> "Selected kotlin"
        "java" ->  "Selected java"
        else -> throw IllegalArgumentException("Not a language")
    }
    println(result) //⇒Selected kotlin
    





 <br/>
 <br/> 
    
   
### 引用  
  
   
   
    
> if式   
> 式の計算結果の真偽で条件分岐を行う   
[AutoHotkeyJp- if式](https://sites.google.com/site/autohotkeyjp/reference/commands/IfExpression)
   
   
   
  
<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
    