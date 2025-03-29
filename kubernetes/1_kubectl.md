```shell
kubectl run webserver --image=nginx:1.14 --port 80

kubectl get pods # 모든 pods 확인
```

```shell
kubectl get pod webserver # webserver pod만 확인

kubectl get pod webserver -o wide
kubectl get pod webserver -o yaml

kubectl exec webserver -it -- /bin/bash

kubectl port -forward webserver 8080:80
```

```shell
kubectl create deployment mainui --image=httpd --replicas=3

kubectl get deployments.apps

kubectl edit deployments.apps mainui

```


## yaml 파일로 pod 생성 예시
```yaml
apiVersion: v1
kind: Pod
metadata:
    name: nginx
    labels:
        app: nginx
        tier: frontend
spec:
    containers:
    - name: nginx
      image: nginx
```