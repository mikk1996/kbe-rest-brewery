Creating K8s deployment:

kubectl create deployment kbe-rest --image springframeworkguru/kbe-rest-brewery --dry-run=client  -o=yaml > deployment.yaml

kubectl create service clusterip kbe-rest --tcp=8080:8080 --dry-run=client -o=yaml > service.yaml

kubectl port-forward service/kbe-rest 8080:8080

curl localhost:8080/actuator/health

