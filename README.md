
**Infra for my k3s cluster**

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update


## kube-prometheus-stack
```bash
helm upgrade --install kube-prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring --create-namespace -f kube-prometheus-stack/values.yaml
```
