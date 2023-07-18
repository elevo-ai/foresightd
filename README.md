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
## Installing foresightd-core chart
```
helm install [RELEASE_NAME] foresightd/foresightd-core
```
## Values

### foresightd-core

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | 107.215.217.233:5000 | The docker image registry to use |
| global.storage_class | string | standard | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| configmap.enabled | boolean | true | Enable or disable configmap |
| core.image_tag | string | 0.0.1 | Image tag for core docker image |
| core.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| core.volume_size | string | 5Gi | Volume size for core |

## Installing foresightd-console chart
```
helm install [RELEASE_NAME] foresightd/foresightd-console
```
## Values

### foresightd-console

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | 107.215.217.233:5000 | The docker image registry to use |
| global.storage_class | string | standard | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| global.foresight_user | string | foresight | Default user to access Jupyter notebook |
| configmap.enabled | boolean | false | Enable or disable configmap |
| console.image_tag | string | 0.0.1 | Image tag for console docker image |
| console.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| console.volume_size | string | 5Gi | Volume size for console |

## Installing foresightd-mlearn chart
```
helm install [RELEASE_NAME] foresightd/foresightd-mlearn
```
## Values

### foresightd-mlearn

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | 107.215.217.233:5000 | The docker image registry to use |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| configmap.enabled | boolean | false | Enable or disable configmap |
| mlearn.image_tag | string | 0.0.1 | Image tag for mlearn docker image |
| mlearn.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| mlearn.volume_size | string | 5Gi | Volume size for mlearn |
| mysql.primary.persistence.storageClass | string | standard | Backend storage |
| mysql.primary.persistence.size | string | 8Gi | Volume size |
| mlflow.image_tag | string | 0.0.1 | Image tag for mlflow docker image |

