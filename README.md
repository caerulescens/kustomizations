# kustomizations

Kustomizations using helm chart generators for local development.

## Install

| Name                                                      |
|-----------------------------------------------------------|
| [kustomize](https://github.com/kubernetes-sigs/kustomize) |
| [helm](https://github.com/helm/helm)                      |

## Configure

Repos:
```shell
helm repo add argo https://argoproj.github.io/argo-helm
helm repo add jetstack https://charts.jetstack.io
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo add kiali https://kiali.org/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo add strimzi https://strimzi.io/charts/
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add rook-release https://charts.rook.io/release
```

## Usage

Build:
```shell
kustomize build --enable-helm .
```

Run:
```shell
helm install --create-namespace --namespace argocd argocd k12s/charts/argo-cd-v7.6.8/argo-cd
kustomize build --enable-helm k12s/app-of-apps/overlays/default | kubectl apply -f -
```
