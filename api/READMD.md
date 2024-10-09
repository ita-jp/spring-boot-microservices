```sh
minikube start --kubernetes-version=v1.31.0
k config current-context

./gradlew bootBuildImage
minikube image load myorg/api:v0.0.2
minikube image ls | grep myorg/api:v0.0.2

k apply -f kubernates/deployment.yaml
k apply -f kubernates/service.yaml

minikube service app-service --url # このプロセスが実行されている間だけ接続できるので Ctrl+C しない
```