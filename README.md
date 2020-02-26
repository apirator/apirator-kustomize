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




