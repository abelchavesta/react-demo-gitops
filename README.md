# react-demo-gitops (FluxCD)

This repo holds Kubernetes manifests for the React demo app.

## Structure
```
clusters/my-cluster/
  flux-system/        # created by `flux bootstrap github ...`
  apps/
    kustomization.yaml  # includes ../../apps/react-demo
apps/react-demo/
  deployment.yaml
  service.yaml
  ingress.yaml
  kustomization.yaml
```

## Apply with Flux
After `flux bootstrap github --owner <YOU> --repository react-demo-gitops --branch main --path clusters/my-cluster --personal`,
Flux will reconcile and apply everything under `clusters/my-cluster`.
