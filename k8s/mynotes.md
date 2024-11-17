database:
kubectl create deploy mysql --image=mysql:5.7 --port 3306 --dry-run=client -o yaml > mysql-deploy.yaml

kubectl expose deploy mysql --port 3306 --dry-run=client -o yaml > mysql-svc.yaml


webserver:

kubectl create deploy webserver --image=alexduncan2100/webserver --port 80 --dry-run=client -o yaml > webserver-deploy.yaml

kubectl expose deploy webserver --port 80 --type NodePort --dry-run=client -o yaml > webserver.yaml