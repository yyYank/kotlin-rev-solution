## KotlinプラグインをIntelliJ IDEAに導入する

### 事前準備
* IntelliJ IDEAのインストール

### プラグイン導入手順

* IntelliJ IDEA起動
* Preferencesを開く（Ctrl(cmd) + カンマもしくはIntelliJ IDEA>Preferences）
* Pluginsを選択する
![図１](http://3.bp.blogspot.com/-IeqtRGH9heA/VP7ejZ5dpPI/AAAAAAAACRE/gCpTiY6K4M0/s1600/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%2B2015-03-10%2B21.06.52.png)
* Install JetBrains Plugin...を選択する
![図２](http://4.bp.blogspot.com/-VsJlgrXtGn0/VP7gGEG8Y2I/AAAAAAAACRU/I5LQ29tsayI/s1600/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%2B2015-03-10%2B21.13.36.png)
* Installを押す
* IntelliJ IDEAを再起動


   
   
これでプラグイン導入は完了です
   

### KotlinでHello Worldしてみよう
* IntelliJ IDEA起動
* New Projectを選択
* 任意のプロジェクトを作成
* プロジェクトを生成
* File>New>Kotlin Fileを選択

### Hello World
   
   こんなかんじで書いてみましょう。
   
    fun main(args : Array<String>) {
        println("hello Kotlin!")
    }
   
   
* Run > Run Default Packageでプログラムを実行。   
   
hello Kotlin!と出力されたら成功です。
   
![図３](http://3.bp.blogspot.com/-d9sU0IkLs8c/VP7l3vS7uLI/AAAAAAAACRg/lSMIbXxoMOg/s1600/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%2B2015-03-10%2B21.38.06.png)  
   
