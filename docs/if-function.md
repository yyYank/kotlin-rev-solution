## ifを式として扱う


Kotlinでのifは単なる条件分岐としての役割だけでなく、   
式として評価するための構文です。


    val hoge = "hoge"
    val result :String = if(hoge == "hoge") { "期待通り" } else { "hogeじゃない"}
    println(result) // => 期待通り

   
   
Stringの戻り値を持つ、処理のように扱うことが出来ます。   
（もちろん、IntでもBigDecimalでも問題ありません）
その場合、最後のステートメントの評価値が変数に代入されます。

   
   
   
{}を省略してこのように書くことも出来ます
   
   
   
   

    val hoge = "hoge"
    val result:String = 
      if(hoge == "hoge")  "期待通り" 
      else  "hogeじゃない"
    println(result) // => 期待通り
   
   
   
   
[条件分岐を行う](../if-statement)で書いた処理も   
厳密にはUnitという戻り値を持たない処理ための型を返しています。
  
   
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
 
