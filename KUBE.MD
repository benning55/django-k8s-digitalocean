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

kubectl create secret generic django-k8s-web-prod-env --from-env-file=/Users/sedthawuth.m/Documents/django-kube-digitalocean/web/.env.prod
kubectl get secret django-k8s-web-prod-env -o YAML

kubectl get serviceaccount default -o YAML (get service account)
```

Ingress troubleshoot

```
kubectl get -n ingress-nginx service
kubectl edit configmap -n ingress-nginx ingress-nginx-controller
kubectl describe certificate echo-tls
```

```
I’m sorry to hear that you are having trouble with cert-manager. There could be several reasons why your website is not accessible with https yet. Here are some possible steps to troubleshoot the issue:

Check if you have a Certificate resource created in your namespace. You can do this by running kubectl get certificate1.
Check if the Certificate resource has a Ready condition set to True. You can do this by running kubectl describe certificate <name>1.
Check if the CertificateRequest resource has a Ready condition set to True. You can do this by running kubectl describe certificaterequest <name>1.
Check if the Secret resource that contains the TLS certificate and key has been created. You can do this by running kubectl get secret <name>1.
Check if your Ingress resource has the correct annotations and references the Secret resource. You can do this by running kubectl describe ingress <name>1.
Check if your DNS records are pointing to the correct IP address or hostname of your Ingress resource2.


kubectl describe challenge


kubectl --namespace default get services -o wide -w ingress-nginx-controller
```

# Process to deploy 1 application

```
Create config
Create Secret
Create Deployment
Create Service

install ingress follow: https://platform9.com/learn/v1.0/tutorials/nginix-controller-via-yaml
install cert manager follow: https://cert-manager.io/docs/installation/kubectl/

get token from cloudflare to access dns01 challenge

apply secret-cloudflare.yaml
apply cluster-issuer.yaml
apply certificate.yaml

write ingress that to map Service for application
```

```
Calling between service

curl nginx-service.default.svc.cluster.local
curl django-service.default.svc.cluster.local
```
