## KotlinをEclipseで動かす
   
   
<font color=red>先に言っておきますと、非推奨です。</font>   
   
     
Kotlinの公式サイトからは現在公表されておらず、   
（昔はcoming soonとか書いてあった） 
   
プラグインは公式リリースされているものではありません（２０１５年３月８日現在）。
   
   
   
素直にIntelliJ IDEAかAndroid Studio使ったほうが楽です。   
一応記録として残しておく程度という認識でお願いします。
   
### 事前準備
* Eclipse 4.3.1(Kepler)以上インストール  
-> Kepler推奨みたいですが、Lunaでも動きました。
* Eclipse SDKインストール
* [kotlin-eclipse](https://github.com/JetBrains/kotlin-eclipse)をgit cloneする   
-> Jet Brains社提供のEclipse SDKのKotlin開発環境

### 手順

１．Eclipseを起動し、File>Import>Project>existing project into workspaceで   
kotlin-eclipseのプロジェクトを取り込む

２．kotlin-eclipseプロジェクトのantスクリプトからkotlin-eclipseをビルドする


３．Kotlin-eclipseのlauncherプロジェクトのlaunch用のantスクリプトを実行



3.の実行時にプラグインを全て追加する必要があります。   
うまく行けばEclipse上にEclipse（Eclipse SDK）が起動するような形になる。   


### 使ってみた感想
   
   Eclipseの良さがあんまり感じられなくなっちゃってる
   
* Eclipse起動してさらにEclipse起動する感じが面倒くさい   
-> 多分環境変数を切り出してantスクリプト実行出来れば良いのだろうけど、   
   JetBrainsさんに頑張ってもらえないと辛い
* コード補完は出来る
* Eclipseの補助的な機能は死んでたりする
   
   

例えば文字列リテラルで   
    String a = "a   
という状態で開業すると   
    String a = "a"   
    + "   
という風にEclipseはしてくれるはずなんだけどKotlin-eclipseだと出来ないとか。




### 参考URL

[動画-Kotlin Eclipse Plugin @clomie #jkug](https://www.youtube.com/watch?v=6AZ6NjWXjzc)   
[スライド-Kotlin Eclipse Plugin #jkug by clomie](https://speakerdeck.com/clomie/kotlin-eclipse-plugin-number-jkug)
