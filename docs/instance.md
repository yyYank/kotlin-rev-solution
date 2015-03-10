## インスタンスを生成する
   
   
   
### フォーマット
   
Kotlinにおいてクラスのインスタンスを生成するには
   
   
    クラス名(コンストラクタ引数)
   
   
の形式で指定します。new演算子は使いません。   
   
  
### 実装サンプル
例えば、以下の様なHogeというクラスが合った時   

    public class Hoge(val message : String) {
       fun printHoge () {
           println("helllo! -> $message")
       }
    }
 
インスタンスの生成は以下のように行います。

    val hoge = Hoge("hoge")
   
   
  
   
   
   
   
   
