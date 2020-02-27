# Kustomize for APIrator backend

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Kustomize receipts to install APIrator backend. It will deploy the operator on kubernetes cluster.

## Usage
[Kustomize](https://kustomize.io/) must be installed to use it.
Please refer to Kustomize [documentation](https://github.com/kubernetes-sigs/kustomize/tree/master/docs) to get started.

## Change the Image Version
On the desired **overlay** (environment) use:
````bash
kustomize edit set image apirator/apirator=apirator/apirator:$TAG_VERSION
````

**TAG_VERSION** is the desired operator version.

## Generate kubernetes manifests

### Development

```bash
kustomize build <folder>/overlays/development
```

## Generate manifests and install

#### Production

It will generate the production manifests and apply on the desired namespace. 

```bash
kustomize build <folder>/overlays/production | kubectl -n <namespace>  apply -f  - 
```

#### Development

It will generate the development manifests and apply on the desired namespace

```bash
kustomize build <folder>/overlays/development | kubectl -n <namespace>  apply -f  - 
```

After run the kustomize stuff you can check the installation running.

### Check installation

```bash
kubectl get deployment -l app=apirator -n <namespace>
```
 
