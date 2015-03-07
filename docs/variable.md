## 変数を宣言する
変数の宣言には2種類の宣言があります

* var
* val
  
varで宣言した場合は可変(mutable)、   
valで宣言した場合は不変(immutable)です   
   
基本的にはvalを使いましょう。
   
   
   
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
  
   
