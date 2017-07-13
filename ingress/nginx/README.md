# Nginxでロードバランサーを作成する

## 手順

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
