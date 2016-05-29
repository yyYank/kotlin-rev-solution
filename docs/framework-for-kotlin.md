
# Kotlinでフレームワークを使いたい

karaというフレームワークもありますが一旦忘れましょう。
下記の2つのフレームワークが筆者の個人的なおすすめです。
全部入りのフレームワークを使いたいならSpringの恩恵が受けられるSpring Boot、
薄いフレームワークで自分で各機能を作っていきたいならwasabi、といった感じでしょうか。



## Spring Boot


### サンプル

公式サイトに載っています。

[Creating a RESTful Web Service with Spring Boot](https://kotlinlang.org/docs/tutorials/spring-boot-restful.html)

### Gradle


    dependencies {
        compile("org.jetbrains.kotlin:kotlin-stdlib:$kotlin_version") // New
        compile("org.springframework.boot:spring-boot-starter-web")
        testCompile("junit:junit")
    }
    
### Maven



    <dependency>
	      <groupId>org.jetbrains.kotlin</groupId>
	      <artifactId>kotlin-stdlib</artifactId>
	      <version>1.0.0</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>1.3.3.RELEASE</version>
    </dependency>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version>
    </dependency>


### 参考サイト

Kotlinのリリースと同じぐらいのタイミングでSpring側がKotlinサポートを発表しています。

[Developing Spring Boot applications with Kotlin](https://spring.io/blog/2016/02/15/developing-spring-boot-applications-with-kotlin)

Getting StartedはSpring Initializr使ったほうが楽だと思う。
[Spring Initializr](https://start.spring.io/#!language=kotlin)



### エントリポイント（アプリ実行）

    @SpringBootApplication
    open class Application {
        companion object {
            @JvmStatic public fun main(args: Array<String>) {
                SpringApplication.run(Application::class.java, *args)
            }
        }
    }
    
このクラスをメインクラスに指定した上で、実行してlocalhost:8080にアクセスすれば
画面が表示されます。
Spring Bootすごい。



## wasabi


wasabiはフルKotlinなHTTPフレームワーク。
主に、httpリクエストのルーティングをコントロールする。
https://github.com/hhariri/wasabi


## Gradle


    repositories {
        // Other repositories you use.
        maven { url 'http://repository.jetbrains.com/all' }
    }

    dependencies {
        // Other dependencies you use.
        compile 'org.wasabi:wasabi:0.1-SNAPSHOT'
    }
    


## コード
    
こんな感じで書くと、ルーティングが出来る。
server.start()で組み込みJettyが起動する。
    
    var server = AppServer()
    
    server.get("/", { response.send("Hello World!") })
    
    server.start()
    
