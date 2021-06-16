# helm-charts

## Test

```sh
helm upgrade -i service-mesh-operators service-mesh-operators/ -n openshift-operators-redhat --create-namespace
```

## Packaging

```sh
helm package service-mesh-operators/
helm repo index --url https://trevorbox.github.io/helm-chart/ .
```
