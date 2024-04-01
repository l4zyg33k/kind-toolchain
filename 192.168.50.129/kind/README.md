Kind 클러스터 만들기
=================

# 클러스터 생성
```shell
kind create cluster -n kind-2 --config cluster.yaml 
```

# Nginx 인그레스
```shell
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```
워커 프로세스 갯수를 1개로 조정
```shell
kubectl patch cm -n ingress-nginx ingress-nginx-controller --type json --patch '[{ "op": "add", "path": "/data/worker-processes", "value": "1" }]'
```

Gitea 도커 레지스트리 푸시를 위한 설정 
```shell
kubectl annotate ing gitea nginx.ingress.kubernetes.io/proxy-body-size=512m

```