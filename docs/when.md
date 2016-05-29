## switchみたいな条件分岐がしたい

### when

Kotlinにはswitch構文はありません。   
代替としてwhenを使います。   
ifと同様にwhenも式（when式）です。

### フォーマット
   
   
以下のように記述します。


    when(引数) {
        値-> 戻り値
        else -> 戻り値
    }
   
elseは必須となっております


### 実装サンプル
   
   
   
よくあるswitch的な書き方だとこんな感じです。
   
    val value = "hoge"
    when(value) {
        "hoge" -> println("ほげ")
        "fuga" -> println("ふが")
        else -> println("piyo")
    }
 

   
   

Stringの戻り値を持つwhenはこのように書きます。


    val value = "hoge"
    val result = when(value) {
        "hoge" -> "ほげ"
        "fuga" -> "ふが"
        else -> "piyo"
    }
    println(result) // => ほげ






<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
