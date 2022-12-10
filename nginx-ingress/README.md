# Nginx-ingress

## Helm

#### From this repository's helm chart

```
helm install nginx-ingress ./helm/nginx-ingress --namespace nginx-ingress
```

#### From Helm Stable repository's helm chart

```
helm repo add nginx-stable https://helm.nginx.com/stable
helm repo update
helm install nginx-ingress nginx-stable/nginx-ingress --namespace nginx-ingress
```


## WithoutHelm

```
kubectl create -f ./withouthelm/deploy.yaml -n nginx-ingress
```