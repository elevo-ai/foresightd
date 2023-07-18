# Aizen Foresight Desktop(foresightd) package

A Helm chart for foresightd platform for machine learning pipelines

## Prerequisites
- Kubernetes 1.25+
- Helm 3.2.0+
- Persistent Volume(PV) provisioner support in the underlying infrastructure

## Get Helm Repository Info
```
helm repo add foresightd https://elevo-ai.github.io/foresightd/charts
helm repo update
```
## Installing the Chart
```
helm install [RELEASE_NAME] foresightd/foresightd-core
```
## Values Files Examples

## Values

### foresightd-core

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | 107.215.217.233:5000 | The docker image registry to use |
| global.storage_class | string | "" | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| configmap.enabled | boolean | true | Enable or disable configmap |
| core.image_tag | string | 0.0.1 | Image tag for core docker image |
| core.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| core.volume_size | string | 5Gi | Volume size for core |

