## AndroidでHello World

せっかくなのでAndroidのアプリで確かめてみましょう。


### 新規プロジェクトを作成
   
   
   
プロジェクトを新規作成します。Anroidバージョンなどは任意のバージョンにし、   
質問に答えながら作成してください。
![新規プロジェクト生成](http://3.bp.blogspot.com/-I03KESEJECA/VQGckLDTS5I/AAAAAAAACTA/kDCCVCemlLI/s1600/hellokotlinandroid1.png)
   
   
   
### KotlinFileを作成

右クリック>Kotlin FileもしくはFile>New>Kotlin FileからKotlinのファイルを生成します。
![Kotlinファイルの生成](http://3.bp.blogspot.com/-aG2xoA01sgw/VQGchBnuN7I/AAAAAAAACSo/kYSXPfWwIjs/s1600/create-koltin-file.png)
   
   
   
### Javaのソースをコピーすると変換してくれます
   
   
   
JavaのソースをKotlinのファイルにコピーすると下図のようなアラートが出て変換してくれます。小ネタです。
![Javaのソースの貼付け](http://2.bp.blogspot.com/-n0arOHKJVVU/VQGcgvRlZ0I/AAAAAAAACSg/MsBSTCuMdzw/s1600/Java-paste.png)
### Kotlinクラス完成
   
とりあえずはonCreateを書けば起動できるのでこのように書いてみます。
   
   

     public class MainActivity : ActionBarActivity {
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main)
            Toast.makeText(this, "Hello Kotlin!!!!", Toast.LENGTH_SHORT).show(), Toast.LENGTH_SHORT).show()
        }
    }

  
   


![Kotlinのコード作成中](http://1.bp.blogspot.com/-huZNU352IeY/VQGcn1Psy_I/AAAAAAAACTQ/2n26DiGtjl0/s1600/kotlinclass.png)

### GradleScriptの自動生成

右上に「Configure Kotlin」というメッセージが出るので、   
as Kotlin(Android with Gradle) moduleというリンクをクリックしてください。   
<font color=red>この時Andorid StudioとGradleのKotlinのバージョンにミスマッチがないか注意して選択するようにしてください。</font>

![Gradleスクリプトの自動生成１](http://4.bp.blogspot.com/-7Jt30Q7GkPU/VQGchDqYAGI/AAAAAAAACSk/EHIUAB9fbY4/s1600/gradle-alert.png)
   
   
   
Gradleスクリプトが自動生成されます。


![Gradleスクリプトの自動生成２](http://4.bp.blogspot.com/-3ptUTHDgWzs/VQGciqyc0TI/AAAAAAAACS4/0k2Fs2uDmbo/s1600/gradle-genereate.png)


### アプリ起動
   
   
RunからRun'アプリ名'を選択し、ローンチします。エミュレータか実機などは設定してください。   

![アプリ起動](http://3.bp.blogspot.com/-xs3VwlVhW2A/VQGcp3ilw-I/AAAAAAAACTY/1vWSZNlpPYk/s1600/%E8%B5%B7%E5%8B%95.png)


Hello Kotlin!!!とトーストで表示されれば完了です。


