# `Replication Controller` 와 `Replica Set`

# Replication Controller 만들기

- rc-definition.yml

```yaml
apiVersion: v1
kind: ReplicationController
metadata: #replicatiotn controller
    name: myapp-rc
    labels:
        app: myapp
        type: front-end
spec:
    template:
        metatdata:
            name: myapp-pod
            labels:
                app: myapp
                type: front-end
            spec:
                containers:
                - name: nginx-container
                  image: nginx
replicas: 3
```