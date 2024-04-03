젠킨스
=====

# 쿠버네티스 플러그인
## 클러스터

### 설정
* Kubernetes URL - https://kubernetes.default.svc.cluster.local
* Kubernetes server certificate key

#### 인증서
```shell
cat ~/.kube/config | yq -r '.clusters[0].cluster."certificate-authority-data"' | base64 -d
```
* Disable https certificate check 체크
* Jenkins URL -  http://jenkins.default.svc.cluster.local:8080 