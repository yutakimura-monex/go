# プロキシ経由で go get を使うためのパッチ
net/http でプロキシのダイジェスト認証(Proxy-Authentication: Digest Access Authentication)を使えるようにするパッチです。

参考: https://github.com/golang/go/issues/29409

## ビルド
`./src/all.bash`

## Docker
GoアプリをビルドするためのDockerイメージを作成できます。
ビルド後に `docker build . -t go-dev:latest` してください。

## 使い方
環境変数にプロキシを設定してください。

```
http_proxy=http://user:password@proxyhost:proxyport/
https_proxy=http://user:password@proxyhost:proxyport/
no_proxy=
```

## 補足事項
- Basic認証はデフォルトで対応しています。このパッチは不要です。環境変数だけ設定すればBasic認証が通ります。
- fork元ブランチは master で、パッチブランチは main です。
