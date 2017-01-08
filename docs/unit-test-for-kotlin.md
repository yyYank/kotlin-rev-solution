
# Kotlinでユニットテストを書く

KotlinでテスティングフレームワークはJUnitかspekなどがあります。
spekは2017年1月9日現在、バージョンは1.1.0-beta2です。(いつの間にメジャーバージョン出たのか)。JUnit5対応もしている。

## JUnit

JUnitは普通に依存関係に入れてください。

### Maven

    <dependency>
    	<groupId>junit</groupId>
    	<artifactId>junit</artifactId>
    	<version>4.12</version>
    </dependency>


### Gradle

    testCompile 'junit:junit:4.12'


### コード

Javaとさほど変わりません。がhamcrest.CorMatchers.isがKotlinの予約語とかぶるので、バッククオート「`」で囲ってあげないといけません。


    import kebab.Browser
    import org.junit.Test
    import org.junit.Assert.assertThat
    import org.hamcrest.CoreMatchers.`is`
    /**
     * Created by yy_yank on 2016/02/27.
     */
    class BrowserTest {
    
        val sut : Browser = Browser()
    
        @Test fun testCalculateURL() {
            val map = mapOf(Pair("1",1), Pair("2",2) , Pair("3", 3))
            val actual = sut.calculateUri("abcd", map)
            assertThat(actual, `is`(""))
        }
    }


assertEqualsとかは普通に何も意識せずに使えます。
はまりどころはこれぐらい。
AssertJなども普通に使えます。


## spek


spekはJetBrains製のKotlinのテスティングフレームワーク。

[http://spekframework.org/docs/latest/](http://spekframework.org/docs/latest/)


Spekクラスを継承してgiven-on-itのスタイルでテストが出来ます。

### Maven
     
    <dependency>
        <groupId>org.jetbrains.spek</groupId>
        <artifactId>spek-api</artifactId>
        <version>1.1.0-beta2</version>
    </dependency>

      

### Gradle 

 build.gradleを以下のように書く
 
    // setup the plugin
    buildscript {
        dependencies {
            classpath 'org.junit.platform:junit-platform-gradle-plugin:1.0.0-M3'
        }
    }

    apply plugin: 'org.junit.platform.gradle.plugin'

    junitPlatform {
        filters {
            engines {
                include 'spek'
            }
        }
    }

    repositories {
        maven { url "http://dl.bintray.com/jetbrains/spek" }
    }

    // setup dependencies
    dependencies {
        testCompile 'org.jetbrains.spek:spek-api:1.1.0-beta3'
        testRuntime 'org.jetbrains.spek:spek-junit-platform-engine:1.1.0-beta3'
    }




build.ktsの場合はこのようにかく


    import org.gradle.api.plugins.ExtensionAware

    import org.junit.platform.gradle.plugin.FiltersExtension
    import org.junit.platform.gradle.plugin.EnginesExtension
    import org.junit.platform.gradle.plugin.JUnitPlatformExtension

    // setup the plugin
    buildscript {
        dependencies {
            classpath("org.junit.platform:junit-platform-gradle-plugin:1.0.0-M3")
        }
    }

    apply {
        plugin("org.junit.platform.gradle.plugin")
    }

    configure {
        filters {
            engines {
                include("spek")
            }
        }
    }

    // setup dependencies
    dependencies {
        testCompile("org.jetbrains.spek:spek-api:1.1.0-beta3")
        testRuntime("org.jetbrains.spek:spek-junit-platform-engine:1.1.0-beta3")
    }

    // extension for configuration
    fun JUnitPlatformExtension.filters(setup: FiltersExtension.() -> Unit) {
        when (this) {
            is ExtensionAware -> extensions.getByType(FiltersExtension::class.java).setup()
            else -> throw Exception("${this::class} must be an instance of ExtensionAware")
        }
    }
    fun FiltersExtension.engines(setup: EnginesExtension.() -> Unit) {
        when (this) {
            is ExtensionAware -> extensions.getByType(EnginesExtension::class.java).setup()
            else -> throw Exception("${this::class} must be an instance of ExtensionAware")
        }
    }




### コード

公式ドキュメントより。

    object SimpleSpec: Spek({
        describe("a calculator") {
            val calculator = SampleCalculator()
            on("addition") {
                val sum = calculator.sum(2, 4)
                it("should return the result of adding the first number to the second number") {
                    assertEquals(6, sum)
                }
            }

            on("subtraction") {
                val subtract = calculator.subtract(4, 2)

                it("should return the result of subtracting the second number from the first number") {
                    assertEquals(2, subtract)
                }
            }
        }
    })



## KotlinTest

これもspekと同じくスペックテスト的なものをするためのライブラリ。ScalaTestに影響を受けている。
[https://github.com/kotlintest/kotlintest](https://github.com/kotlintest/kotlintest)

### Maven

    <dependency>
        <groupId>io.kotlintest</groupId>
        <artifactId>kotlintest</artifactId>
        <version>xxx</version>
        <scope>test</scope>
    </dependency>


### Gradle

    testCompile 'io.kotlintest:kotlintest:xxx'


### コード


公式ドキュメントより。

    class StringSpecExample : StringSpec() {
        init {
            "strings.length should return size of string" {
                "hello".length shouldBe 5
            }
        }
    }
