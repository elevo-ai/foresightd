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
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | 0.0.1 | Default tag for the image |
| global.storage_class | string | standard | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| configmap.enabled | boolean | true | Enable or disable configmap |
| core.image_tag | string | 0.0.1 | Image tag for core docker image |
| core.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| core.volume_size | string | 5Gi | Volume size for core |
| core.resources.limits.cpu | string | 1 | Max cpu |
| core.resources.limits.memory | string | 4Gi | Max memory |

## Installing foresightd-console chart
```
helm install [RELEASE_NAME] foresightd/foresightd-console
```
## Values

### foresightd-console

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | 0.0.1 | Default tag for the image |
| global.storage_class | string | standard | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| global.foresight_user | string | foresight | Default user to access Jupyter notebook |
| configmap.enabled | boolean | false | Enable or disable configmap |
| console.image_tag | string | 0.0.1 | Image tag for console docker image |
| console.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| console.volume_size | string | 5Gi | Volume size for console |
| console.resources.limits.cpu | string | 200m | Max cpu |
| console.resources.limits.memory | string | 2Gi | Max memory |

## Installing foresightd-mlearn chart
```
helm install [RELEASE_NAME] foresightd/foresightd-mlearn
```
## Values

### foresightd-mlearn

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | 0.0.1 | Default tag for the image |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| configmap.enabled | boolean | false | Enable or disable configmap |
| mlearn.image_tag | string | 0.0.1 | Image tag for mlearn docker |
| mlearn.imagepullpolicy | string | IfNotPresent | Pull policy for docker image |
| mlearn.volume_size | string | 5Gi | Volume size for mlearn |
| mysql.primary.persistence.storageClass | string | standard | Backend storage |
| mysql.primary.persistence.size | string | 8Gi | Volume size |
| mlflow.image_tag | string | 0.0.1 | Image tag for mlflow docker image |
| mlflow.resources.limits.cpu | string | 200m | Max cpu |
| mlflow.resources.limits.memory | string | 2Gi | Max memory |
| mlearn.resources.limits.cpu | string | 2 | Max cpu |
| mlearn.resources.limits.memory | string | 4Gi | Max memory |

