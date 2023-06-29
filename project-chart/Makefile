host-kube:
	eval $(minikube docker-env)
	docker build -t host-app ../../host-service/hotel-host-service/
	helm install -f host_values.yaml host-backend .

host-dockerize:
	docker build -t host-app ../../host-service/hotel-host-service/

dry-host-kube:
	helm install -f host_values.yaml --dry-run host-backend .

host-deploy:
	helm install -f host_values.yaml host-backend .
	
host-forward:
	kubectl port-forward svc/host-app-service 8080:8080

host-kube-update:
	helm upgrade -f host_values.yaml --dry-run host-backend .

host-rollback:
	helm rollback host-backend

host-uninstall:
	helm uninstall host-backend

jaeger:
	kubectl create -f https://github.com/jaegertracing/jaeger-operator/releases/download/v1.46.0/jaeger-operator.yaml -n observability


cert-manager:
	kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.6.3/cert-manager.yaml
