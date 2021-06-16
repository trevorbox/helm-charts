# Helm Charts

Common charts used for many different projects.

## Service Mesh Operators

Installs the following Subscriptions in Openshift:

* Openshift Service Mesh
* Elasticsearch
* Jaeger
* Kiali

### Installation

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm repo update
helm upgrade --install service-mesh-operators trevorbox/service-mesh-operators \
  --namespace openshift-operators-redhat \
  --create-namespace
```

### Test

```sh
helm upgrade -i service-mesh-operators service-mesh-operators/ -n openshift-operators-redhat --create-namespace
```

### Packaging

```sh
helm package service-mesh-operators/
helm repo index --url https://trevorbox.github.io/helm-chart/ .
```
