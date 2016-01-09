## 配列を生成する


配列の利用は、Arrayクラスのインスタンスを生成します。


### フォーマット

説明をとても省略して簡単に言うと、以下のフォーマットで
配列を作成します。

    Array<型名>(要素の数, {初期化処理})


### 実装サンプル

実際には以下のように宣言します。
(偶数を宣言しています)

    // [0, 2, 4 , 6, 8, 10, 12, 14, 16, 18]
    val evenNumbers = Array<Int>(10, {it * 2})


### array, listOf, arrayListOf, linkedListOf

配列の宣言にはKotlinの標準ライブラリとして以下の関数が提供されています。
   
   
   

   
#### array   
Arrayインスタンスを簡易に生成
#### listOf   
java.util.Listを生成。要素を変更できません。
#### arrayListOf   
java.util.ArrayListインスタンスを生成。Javaと同様に追加、削除などが可能。
#### linkedListOf   
java.util.LinkedListインスタンスを生成。Javaと同様に追加、削除などが可能。
   
arrayListという関数もあったようですが、非推奨になっています。  
   
   
   
   
### 実装サンプル
    val oddNumbers = array(1, 3, 5, 7, 9)
    val list = listOf(1,2,3,4,5)
    val arrayList = arrayListOf(1,2,3,4,5)
    val linkedList = linkedListOf(1,2,3,4,5)
  
  
   
   
   
   
   
   
<br/>
<br/>
<br/>
<br/>
<br/>
#### ページ公開時のKotlinのバージョン
   
0.10.195 
 
