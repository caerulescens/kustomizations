# kustomizations

Kustomizations using helm chart generators for local development.

## Install

| name                                                      |
|-----------------------------------------------------------|
| [kustomize](https://github.com/kubernetes-sigs/kustomize) |
| [helm](https://github.com/helm/helm)                      |
| [pre-commit](https://github.com/pre-commit/pre-commit)    |

Configure:
```shell
pre-commit install
```

## Usage

Build:
```shell
kustomize build --enable-helm k12s/
```

Run:
```shell
helm install --create-namespace --namespace argocd argocd k12s/charts/argo-cd-v5.49.0/argo-cd
kustomize build --enable-helm k12s/app-of-apps/overlays/default | kubectl apply -f -
```

Check:
```shell
pre-commit run
```
