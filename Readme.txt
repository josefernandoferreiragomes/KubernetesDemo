reference original source code
https://gitlab.com/nanuchi/k8s-in-1-hour

step by step:
	install mk
		https://minikube.sigs.k8s.io/docs/start/
			Download and run the installer for the latest release.

	start mk
		C:\Program Files\Kubernetes\Minikube
			minikube start --driver docker

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

	applying the configuration files
		kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo-config.yaml
		kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo-secret.yaml
		kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\mongo.yaml
		kubectl apply -f C:\Users\josefgom\Documents\Exercicios\kubernetesDemo\webapp.yaml

	check status
		kubectl get all

	get ip
		kubectl get node -o wide

	open in browser
		http://192.168.49.2:30100/

	if error
		minikube service webapp-service

Rerun after exercise complete, or pulled from git:
	start mk		
		minikube start --driver docker

	applying the configuration files
		kubectl apply -f mongo-config.yaml
		kubectl apply -f mongo-secret.yaml
		kubectl apply -f mongo.yaml
		kubectl apply -f webapp.yaml

	check status
		kubectl get all

	get ip
		kubectl get node -o wide

	if error
		minikube service webapp-service

	open in browser
		http://127.0.0.1:53409/

other commands:
	minikube status
	kubectl get node
	kubectl get all
	kubectl get configmap
	kubectl get secret
	kubectl get pod
	kubectl --help
	kubectl get --help
	kubectl describe service webapp-service
	kubectl describe pod/mongo-deployment-7fcd9df58d-6kmmt

	get ip
		Minikube ip
			or
		kubectl get node -o wide

	kubectl logs webapp-deployment-9fccd564d-gfwpw
	kubectl get svc		

	if error
		minikube service webapp-service

		it will list ip and port

	minikube stop

	delete deployments, to delete it all
		kubectl delete deployment mongo-deployment
		kubectl delete deployment webapp-deployment