# Nginxでロードバランサーを作成する (Let's EncryptでSSL化)

## 手順

設定を変更

1. ingress.yml内のホスト名を自分のものに編集
1. tls-configmap.yml内のメールアドレスを自分のものに編集

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
