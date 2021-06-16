# helm-charts

Common charts used for many different projects.

## service-mesh-operator

Installs the Service Mesh operator Subscriptions in Openshift

### installation

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm upgrade --install service-mesh-operators trevorbox/service-mesh-operators \
  --namespace openshift-operators-redhat \
  --create-namespace
```

## local test

```sh
helm upgrade -i service-mesh-operators service-mesh-operators/ -n openshift-operators-redhat --create-namespace
```

### local packaging

```sh
helm package service-mesh-operators/
helm repo index --url https://trevorbox.github.io/helm-chart/ .
```
