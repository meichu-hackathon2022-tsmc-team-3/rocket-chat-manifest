# Rocket Chat App Manifest

## Requirement

- Helm v3
- K8s cluster

## installation

1. change config in values.yaml

2. setup rocket chat db secret

```
apiVersion: v1
kind: Secret
metadata:
  name: chat-db-secret
  namespace: chat
data:
  MONGO_URL: <MONGO_URL>
  MONGO_OPLOG_URL: <MONGO_OPLOG_URL>
```

3. apply db secret

```
kubectl apply -f <your_secret.yaml>
```

4. install helm application

```
helm install rocket-chat-app .
```