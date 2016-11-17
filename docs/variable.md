## 変数を宣言する
変数の宣言には2種類の宣言があります

* var
* val
  
varで宣言した場合は変数への再代入可能です。    
valで宣言した場合は変数への再代入はできません。



    var hoge = "a"
    hoge = "b"  //OK
    val fuga = "a"
    fuga = "b"  // コンパイルエラー
   
varはいつでもどこでも代入できてしまいます。    
valで宣言すると再代入時にコンパイルエラーにしてくれます。    
代入を何度も繰り返す破壊的代入は良くないので、    
基本的にはvalを使いましょう
    
<font color=red>※varを使わざるを得ないケースもあります</font>
   
   
   
### 文字列の宣言

    // 文字列の宣言
    val hoge = "aiueo"
    // 型の宣言も可能
    val hoge : String = "aiueo"
    // 数値の宣言
    val number = 1
      
型の宣言は明示的にすることも可能ですが、   
推論されるので宣言しなくても良いです。



### nullは?を付けないと代入できない

    // コンパイルエラー!
    val a = null
    // これならnullを代入してもOK
    val a : String? = null

こういうこと言われてしまいます   
「 is not satisfied: inferred type kotlin.Nothing? is not a subtype of kotlin.Any」    
null使わないほうがいいですね   
    
   
どうしてもnullを許容するためには型を宣言して「?」を付ける必要があります。
  
   
   
   
   
   
   
   
   
<br/>
<br/>
<br/>
<br/>
   
   
   
   
   
   
   
   
    
