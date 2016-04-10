

# Kotlinでtry-with-resourcesが使いたい 



useを使います。

    val inputStream = Thread.currentThread().contextClassLoader.getResourceAsStream("hogehoge")
    java.io.InputStreamReader(inputStream).use {
        // `it`がInputStreamReaderのインスタンス
        val b = it.read()
    }
