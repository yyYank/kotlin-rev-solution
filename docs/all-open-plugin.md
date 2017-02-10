
# クラスの継承をデフォルトで可能にしたい

all openプラグインを利用します。

## 利用できるversion

1.1以降


## 使い方

build.gradleに以下を追記してください。
明示的なopenが不要になり、デフォルトでclassがopen(継承可能)となります。

```
allOpen {
    annotation('io.realm.annotations.RealmClass')
}
```

## 用途

DIライブラリ、Mockitoなどとの組み合わせ
