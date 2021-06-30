# Helm Charts

Common charts used for many different projects.

## Service Mesh Operators

Installs the following Subscriptions in Openshift:

* Openshift Service Mesh
* Elasticsearch
* Jaeger
* Kiali

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm repo update
helm upgrade --install service-mesh-operators trevorbox/service-mesh-operators \
  --namespace openshift-operators-redhat \
  --create-namespace
```

## Service Mesh Control Plane (SMCP)

This is a simplified service mesh control plane deployment example. Consider this a starting point to [pull](https://helm.sh/docs/helm/helm_pull/) from locally and repackage for your needs.

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm repo update
helm upgrade --install smcp trevorbox/smcp \
  --namespace istio-system \
  --create-namespace
```

## Bookinfo Istio Configurations

Basic Istio configurations for Bookinfo.

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm repo update
helm upgrade --install bookinfo-istio trevorbox/bookinfo-istio \
  --namespace bookinfo \
  --set gateway.host=$(oc get route api -o jsonpath={.spec.host} -n istio-system) \
  --create-namespace
```

## Bookinfo

An application for testing Istio.

```sh
helm repo add trevorbox https://trevorbox.github.io/helm-charts
helm repo update
helm upgrade --install bookinfo trevorbox/bookinfo \
  --namespace bookinfo \
  --create-namespace
```
