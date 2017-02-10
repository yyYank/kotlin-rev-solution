
# クラスの継承をデフォルトで可能にしたい

all openプラグインを利用します。

## 利用できるversion

1.1以降


## 使い方

build.gradleに以下を追記してください。
明示的なopenが不要になり、デフォルトでclassがopen(継承可能)となります。

```
allOpen {
    annotation('クラスの完全修飾子名')
}
```

## 用途

DIライブラリ、Mockitoなどとの組み合わせ

## 参考URL

*[http://taro.hatenablog.jp/entry/2016/12/28/105949](http://taro.hatenablog.jp/entry/2016/12/28/105949)
* [http://stackoverflow.com/questions/41462180/kotlin-all-open-compiler-plugin-doesnt-work](http://stackoverflow.com/questions/41462180/kotlin-all-open-compiler-plugin-doesnt-work)
