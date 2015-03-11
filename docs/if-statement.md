## 条件分岐を行う


他のプログラミング言語と同様にifを使います。   
Kotlinのifは単なる条件分岐ではなく、式（if式）です。   
これについては[ifを式として扱う](./if-function)参照。

その他に[when](../when)などで条件を分岐する方法もあります。   
（whenも厳密には式です）   
   

### フォーマット

if、else if、elseで条件が分岐できます。

    if(条件) {
        処理
    } else if(条件){
        処理
    } else {
        処理
    }


### 実装サンプル

    val value  = 1


    if(value == 1) {
        println("value is one")
    } else if(value == 2){
        println("value is two")
    } else {
        println("other value")
    }
<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
