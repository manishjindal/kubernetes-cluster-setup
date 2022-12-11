# Nginx-ingress
The NGINX Ingress Controller an implementation of a Kubernetes Ingress Controller for NGINX and NGINX Plus.

## What is Ingress?
The Ingress is a Kubernetes resource that lets you configure an HTTP load balancer for applications running on Kubernetes, represented by one or more Services. Such a load balancer is necessary to deliver those applications to clients outside of the Kubernetes cluster.


## Helm
You can install nginx-ingress control by using helm chart, you can use the helm chart directly from the helm stable repo (latest) or one from this repository which is updated on timely manner.

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
You can also create the ingress controller by directly using deploy.yaml file, note that this yaml is for dpeloying nginx-ingress on `digital-ocean` kubernetes cluster, if you plan to deploy this on any other cloud platform please update the `annotations` accordingly.

```
kubectl create -f ./withouthelm/deploy.yaml -n nginx-ingress
```