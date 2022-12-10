# Monitoring
This repository contains two helm chart `kube-prometheus-stack` and `prometheues-msteams` and configs folder.

config folder again is devided into `global` and `envs`.
* global: consider keeping all variable components in this file which can be used in all the environments.
* envs: keep environment specific variables in this folder under separate subfolder (one per each environment)

## kube-prometheus-stack
Kube-prometheus stack chart deploys following components:
* grafana
* prometheus
* alertmanager

### steps to deploy chart 

#### From this repository's helm chart
```
helm install kube-prometheus-stack ./kube-prometheus-stack --namespace monitoring
```

Using variable file 

```
helm install kube-prometheus-stack ./kube-prometheus-stack --values ./configs/globals/kube-prometheus-stack.yml --values ./configs/envs/dev/kube-prometheus-stack.yml --namespace monitoring
```

#### From Helm repository's helm chart



## prometheus-msteams
By default `alertmanager` doesn't support alerting to msteams.

To enable msteams alerting, you can deploy `prometheus-msteams` helm chart which exposes `prometheus-msteams` endpoint where alertmanager can send alerts and then this chart further sends alerts to configured msteams channel as mentioned in`./config/envs/dev/prometheus-msteams.yml` file.


### Deploy prometheus
```
helm install prometheus-msteams ./prometheus-msteams --values ./configs/globals/prometheus-msteams.yml --values ./configs/envs/dev/prometheus-msteams.yml --namespace monitoring
```

