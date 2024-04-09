# Deploy Backstage in K8s

## Commands

```sh
kubectl create namespace backstage
```

### Postgres Deploy

Secrets must be saved as base64

```sh
echo -n secret-value | base64  
```

Then run following commands

```sh
kubectl apply -f postgres/postgres-secrets.yaml
kubectl apply -f postgres/postgres-storage.yaml
kubectl apply -f postgres/postgres.yaml
kubectl apply -f postgres/postgres-service.yaml
```

### Backstage Local Image
Remember to paste all app-config.production.yaml content into app-config.yaml, then run:

```sh
docker image build -t backstage:1.0.0 .
```

### Backstage Deploy
```sh
kubectl apply -f backstage/backstage-secrets.yaml
kubectl apply -f backstage/backstage.yaml
kubectl apply -f backstage/backstage-service.yaml
```

After that, run the following command
```sh
sudo kubectl port-forward --namespace=backstage svc/backstage 80:80
```
### Finish All

```sh
kubectl delete -n backstage deployment --all
```
