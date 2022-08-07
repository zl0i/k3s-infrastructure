
**Infra for my k3s cluster**

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo add jetstack https://charts.jetstack.io
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update


## Ingress nginx
```
helm upgrade --install ingress-nginx ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace -f ingress-nginx/values.yaml --version 4.2.0
```

## Cert Manager
```
helm upgrade --install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace -f cert-manager/values.yaml --version v1.9.1
```

## Prometheus 
```
helm upgrade --install prometheus prometheus-community/prometheus --namespace monitoring --create-namespace -f prometheus/values.yaml --version 15.11.0
```

## Blackbox Exporter
```
helm upgrade --install prometheus-blackbox-exporter prometheus-community/prometheus-blackbox-exporter --namespace monitoring --create-namespace -f prometheus-blackbox-exporter/values.yaml --version 6.0.0
```

## Loki
```
helm upgrade --install loki grafana/loki --namespace logs --create-namespace -f loki/values.yaml --version 2.13.3
```

## Promtail
```
helm upgrade --install promtail grafana/promtail --namespace logs --create-namespace -f promtail/values.yaml --version 6.2.2
```

## Grafana 
```
helm upgrade --install grafana grafana/grafana --namespace monitoring --create-namespace -f grafana/values.yaml --version 6.32.9
```
