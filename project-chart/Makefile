host-kube:
	eval $(minikube docker-env)
	docker build -t host-app ../../host-service/hotel-host-service/
	helm install -f host_values.yaml host-backend .

host-dockerize:
	docker build -t host-app ../../host-service/hotel-host-service/

dry-host-kube:
	helm install -f host_values.yaml --dry-run host-backend .

host-kube-update:
	helm upgrade -f host_values.yaml --dry-run host-backend .

host-rollback:
	helm rollback host-backend

host-uninstall:
	helm uninstall host-backend