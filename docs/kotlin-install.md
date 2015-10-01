## Kotlinをインストールする
   
   
KotlinをIDE(統合開発環境)などを介さずに実行するためには   
Kotlin Compilerをダウンロードする必要があります。   
   
   
   
2015年3月現在、kotlin-compiler-0.10.195.zipとして   
ダウンロードできます。   
   
   
   
[Kotlinの公式サイト](http://kotlinlang.org/)からダウンロードしましょう。   
   
   
なお、IDEを使う場合はこの作業は必要ないです。   
   
   
### 準備
   
   環境変数にKOTLIN_HOME/binを通してください。


### 使えるコマンド

* kotlinc
* kotlinc-jvm
* kotlinc-js

kotlincはkoltin-jvmのAlias。つまり、一緒なので   
kotlincを使えば間違えないです。   
   
   
   
#### kotlinc（kotlinc-jvm）
   
   
以下のフォーマットでコマンドは使えます。

    kotlinc ＜ファイル名＞ ＜オプション＞
   
具体的には、こんな感じ。

    kotlinc-jvm hello.kt -include-runtime -d hello.jar

   コンパイル時はkotlincですが、実行時はkotlinコマンドはないです。
   つまりこういうこと。

    java -jar hello.jar

-include-runtimeでKotlinの実行ランタイムが内包される。   
これがないと動かない。   
   

kotlincのオプションは以下のとおり


    -d <directory|jar>         jarとして出力するファイルパスを指定
    -classpath (-cp) <path>    読み込ませたいclass filesが存在するパスを指定
    -annotations <path>        external annotationsをパスに含む
    -include-runtime           Kotlinのランタイムをjarに含む
    -no-jdk                    Java runtimeをクラスパスに含まない
    -no-stdlib                 Kotlin runtimeをクラスパスに含まない
    -no-jdk-annotations        JDK external annotationsをクラスパスに含まない
    -module <path>             コンパイルするモジュールを指定
    -script                    Scriptのファイルを評価する
    -kotlin-home <path>        KotlinランタイムのHOMEを指定（annotationとruntime librariesを見つけるため）
    -nowarn                    警告を表示しない
    -verbose                   verboseログ出力を有効にする
    -version                   バージョン確認
    -help (-h)                 HELP表示
    -X                         advancedオプション表示


   
   
   
kotlincだけ打ち込むとREPL（対話環境モードになる）


#### kotlinc-js


kolinc-jsにはREPLはないようです。   
動作確認はしていないが以下の様なコマンドで   
JavaScriptにコンバートされるよう。

    kotlinc-js -output test -sourceFiles test.kt -libraryFiles kotlin-jslib.jar
  
   
   
オプションは以下のとおり。

    -output <path>             出力ファイルパス
    -no-stdlib                 Kotlinのシステムライブラリを使わない
    -library-files <path[,]>   zipされたライブラリまたはkotlinファイルをカンマ繋ぎでパス指定
    -source-map                ソースマップを生成
    -target <version>          ECMA標準のファイルを生成(ECMA 5のみサポート)
    -main {call,noCall}        main関数を実行するかどうか（デフォルトは実行）
    -output-prefix <path>      出力ファイルにprefixを追加する
    -output-postfix <path>     出力ファイルにpostfixを追加する
    -nowarn                    警告を表示しない
    -verbose                   verboseログ出力を有効にする
    -version                   バージョン確認
    -help (-h)                 HELP表示
    -X                         advancedオプション表示



### コンパイラ構成
   

#### bin

* kotlinc
* kotlinc-js.bat
* kotlinc-jvm.bat
* kotlinc-js
* kotlinc-jvm
* kotlinc.bat


#### lib
   
* kotlin-android-sdk-annotations.jar
* kotlin-jslib.jar
* kotlin-ant.jar
* kotlin-preloader.jar
* kotlin-compiler.jar
* kotlin-runtime-sources.jar
* kotlin-jdk-annotations.jar
* kotlin-runtime.jar
* kotlin-jslib-sources.jar


だいたいこんな感じです。




参考


[公式チュートリアル](http://kotlinlang.org/docs/tutorials/command-line.html)

[あまり知られていない？ #Kotlin の対話型評価環境](http://taro.hatenablog.jp/entry/2013/04/06/162855)
