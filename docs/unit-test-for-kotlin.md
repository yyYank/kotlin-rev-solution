
# Kotlinでユニットテストを書く

KotlinでテスティングフレームワークはJUnitかspekなどがあります。

## JUnit

JUnitは普通に依存関係に入れてください。

### Maven

    <dependency>
    	<groupId>junit</groupId>
    	<artifactId>junit</artifactId>
    	<version>4.12</version>
    </dependency>


### Gradle

    'junit:junit:4.12'


### コード

Javaとさほど変わりません。がhamcrest.CorMatchers.isがKotlinの予約ごとかぶるので、バッククオート「`」で囲ってあげないといけません。


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

http://jetbrains.github.io/spek/


Spekクラスを継承してgiven-on-itのスタイルでテストが出来ます。

### Maven

あとで書く

### Gradle 

あとで書く

### コード

公式ドキュメントより。

    class TaxCalculatorSpecs: Spek() { init {
    
        given("Tax rate calculator with default locale settings") {
            val taxRateCalculator = TaxRateCalculator()
            on("calculating the rate for an income of 200 and an average change of 10 per semester") {
                val value = taxRateCalculator.calculateRate(200, 10)
                it("should result in a value of 300") {
                    assertEquals(300, value)
                }
            }
        }
    }}
