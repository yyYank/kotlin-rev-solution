## switchみたいな条件分岐がしたい

### when

Kotlinにはswitch構文はありません。   
代替としてwhenを使います。   
ifと同様にwhenも式（when式）です。
これについては[制御構文を式として扱う](./return-on-statement)参照。

### フォーマット
   
   
以下のように記述します。



    when(引数) {
        値-> {戻り値}
        else -> {戻り値}
    }
   
elseは必須で、引数がどの値にも等しくない時に呼ばれます.


### 実装サンプル
   
   
   
よくあるswitch的な書き方だとこんな感じです。
   
    val value = "hoge"
    when(value) {
        "hoge" -> println("ほげ")
        "fuga" -> println("ふが")
        else -> println("piyo")
    }
 

   
  


<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
