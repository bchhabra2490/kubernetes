## Neo4j deployment
```
kubectl create namespace test
kubectl apply -f gce-ssd-storageclass.yaml
gcloud compute disks create --size 50GB --type pd-ssd pd-ssd-disk-1 --zone=us-central1-a
kubectl apply -f neo4j-pvc.yaml
```
``` 
- kubectl apply -f neo4j-deployment.yaml
- kubectl apply -f neo4j-service.yaml
```

- Now run `kubectl get svc` and copy the **External-IP**.
- Go to `External-IP:7474` in the browser. You will see the Neo4j Interface.
- Credentials
    - username: neo4j
    - password: neo4j