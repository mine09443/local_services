init: 
	@gcloud container clusters get-credentials gke-load-test --zone asia-east1-b --project abc.com:my-project

scale:
	@kubectl scale deployment/locust-worker --replicas=20

up:
	@kubectl apply -f kubernetes-config/locust-worker-controller.yaml
	@kubectl apply -f kubernetes-config/locust-master-service.yaml

stat:
	@kubectl get pod
	@kubectl get deploy
	@kubectl get service

clean: 
	@kubectl delete service locust-master
	@kubectl delete deploy locust-worker

.PHONY: init up clean stat scale
