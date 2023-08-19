# Command

# MAIN APPLY

```
kubectl apply -f k8s/apps/django-k8s-web.yaml
```

```
Deployment

kubectl get deployments
kubectl get pods
kubectl delete pods <pod-name>
kubectl exec -it <pod-name>  -- /bin/bash
kubectl delete -f ./k8s/nginx/deployment.yaml


kubectl apply -f k8s/nginx/deployment.yaml
```

```
Service

kubectl get service

kubectl apply -f k8s/nginx/service.yaml

dop_v1_2d120b030dd0a6f7a65e37a14162408f5686a01675bb784ded20757c5655bbe6
```

```
Combo file

deployment

---

service


```

```
Secrets add

kubectl create secret generic django-k8s-web-prod-env --from-env-file=.env.prod
kubectl get secret django-k8s-web-prod-env -o YAML

kubectl get serviceaccount default -o YAML (get service account)
```
