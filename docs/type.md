## 型を宣言する
型の宣言は変数の後に:(コロン) + 形名で表現します。
関数の戻り値の型指定に関しても同様です。

   
   
### 型の宣言(変数)

    val hoge : String = "a"
    val fuga : Int = 1
    val piyo : Double = 1.0
      
型は基本的に大文字始まりです。
Javaではintやdoubleなどプリミティブものは小文字始まりですが、
Kotlinでは全てをクラスとして扱います。




### 型の宣言(関数)

    fun createHogeString() : String = "Hoge" 


関数の型宣言も同様に:(コロン) + 型名でで表現します。




### null許容型の宣言


[変数の宣言の項](../variable)でも説明しましたが、   
Kotlinでは基本的にnull（何も値が無い状態）を許容しません。    

nullを許容する場合には:（コロン） + 型名のあとに「？」をつけます。

    val hoge : String? = null // OK
    val hoge : String = null // コンパイルエラー
 

    fun nullValue() : String? = null // OK
    fun nullValue() : String = null // コンパイルエラー

基本的にはnull許さないよう言語設計されています。

     
   
   
<br/>  
<br/>  
<br/>  
<br/>  
NULL
>NULLはNULL値（あるいは空値）と呼ばれることもあるが、
>コッドによると値ではない（特殊な値や例外的な値ではない）。
>値ではないので型もない。
>整数型の列にあるNULLも文字列型の列にあるNULLも同じNULLであり、
>NULL整数・NULL文字列などの区別はない。 
>内部的にはNULLは、（NaNやヌルポインタのような）特定のビット列ではなく、
>値とは別個の「NULLかどうか」を表すメモリ領域で管理されていることが多い。
   
（Wikipediaより）
