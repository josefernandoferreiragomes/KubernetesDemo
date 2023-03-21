https://gitlab.com/nanuchi/k8s-in-1-hour

C:\Program Files\Kubernetes\Minikube
minikube start --driver docker

minikube status

kubectl get node

mongo-config.yaml
	https://kubernetes.io/docs/concepts/configuration/configmap/

mongo-secret.yaml
	mongouser
	mongopassword
	https://kubernetes.io/docs/concepts/configuration/secret/

mongo.yaml
	https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
	https://hub.docker.com/_/mongo/tags?page=1&name=5.0
	https://kubernetes.io/docs/concepts/services-networking/service/
	https://hub.docker.com/_/mongo

webapp.yaml
	copy of mongo.yaml, but replacing mongo for webapp
	https://hub.docker.com/r/nanajanashia/k8s-demo-app/tags

kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo-config.yaml
kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo-secret.yaml
kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo.yaml
kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\webapp.yaml

kubectl get all
kubectl get configmap
kubectl get secret
kubectl get pod
kubectl --help
kubectl get --help
kubectl describe service webapp-service
kubectl describe pod/mongo-deployment-7fcd9df58d-6kmmt

Minikube ip
	or
kubectl get node -o wide

kubectl logs webapp-deployment-9fccd564d-gfwpw
kubectl get svc

kubectl get node
kubectl get node -o wide

in browser
http://192.168.49.2:30100/

if error
minikube service webapp-service

it will list ip and port

minikube stop

delete deployments, to delete it all
kubectl delete deployment mongo-deployment
kubectl delete deployment webapp-deployment