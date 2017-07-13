# Nginxでロードバランサーを作成する

## 手順

設定を変更

1. GCPコンソールから80と443を許可するようファイヤウォールの設定を行う。
  ※ターゲットタグはインスタンステンプレートに設定されているネットワークタグの値を使うといい。


kubernetesにデプロイ

```
kubectl -f ./
```

IPアドレスを確認

```
kubectl describe ing --namespace ingress-test
```

アクセスする

```
# echoheaderコンテナにアクセス
curl -H 'Host: service.example.com' IPアドレス

# default-http-backendコンテナにアクセス
curl IPアドレス
```
