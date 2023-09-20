# containersensor

Used by Darktrace/DETECT customers to install containerSensor & optionally osSensor in their Kubernetes clusters

![Version: 1.0.7](https://img.shields.io/badge/Version-1.0.7-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

## Prerequisites

To install this Helm Chart, you must be an active Darktrace customer with a vSensor installed in the same network as the Kubernetes cluster which will be monitored.

## Installation Instructions

```console
helm repo add darktrace https://darktrace-com.github.io/helm-charts
helm install containersensor darktrace/containersensor \
    --namespace darktrace \
    --create-namespace \
    --set vSensorHmacKey=<vSensor configured HMAC key> \
    --set vSensorHostname=<vSensor Hostname>
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| containerSensor.affinity | object | `{}` | Define affinity for containerSensor Deployment |
| containerSensor.annotations | object | `{}` | Annotations added to containerSensor resources |
| containerSensor.clusterRole.create | bool | `true` | Creates containerSensor ClusterRole |
| containerSensor.clusterRoleBinding.create | bool | `true` | Creates containerSensor ClusterRoleBinding |
| containerSensor.config.defaultConfig | string | Please consult values.yaml | Configuration for tracking by pod images in K8s |
| containerSensor.config.provisionConfig | int | `1` | Set Provision Config Level |
| containerSensor.configMap.create | bool | `true` | Creates containerSensor ConfigMap |
| containerSensor.create | bool | `true` | Creates containerSensor Deployment |
| containerSensor.extraEnvs | list | `[]` | Define extra environment variables for containerSensor Deployment |
| containerSensor.image.name | string | `"darktrace/containersensor"` | Image name |
| containerSensor.image.pullPolicy | string | `"Always"` | Image pullPolicy |
| containerSensor.image.pullSecrets | object | `{}` | Image pullSecret |
| containerSensor.image.tag | string | `"1"` | Image tag |
| containerSensor.labels | object | `{}` | Labels added to containerSensor resources |
| containerSensor.nodeSelector | object | `{}` | Define nodeSelector for containerSensor Deployment |
| containerSensor.podReplicas | string | `"1"` | Set number of replicas for containerSensor Deployment |
| containerSensor.resources | object | `{}` | Override resources for containerSensor Deployment |
| containerSensor.secret.create | bool | `true` | Disable if creating the secret separate from Helm Chart installation |
| containerSensor.secret.overrideValue | string | `""` | Optional override for the Darktrace Token value used by containerSensor |
| containerSensor.serviceAccount.create | bool | `true` | Creates containerSensor ServiceAccount |
| containerSensor.tolerations | list | `[]` | Define tolerations for containerSensor Deployment |
| nameOverride | string | `""` |  |
| osSensor.affinity | object | `{}` | Define affinity for osSensor Daemonset |
| osSensor.annotations | object | `{}` | Annotations added to the osSensor resources |
| osSensor.config.antigena.enabled | bool | `false` | Boolean value to enable Antigena capabilities |
| osSensor.config.configPath | string | `""` | Path for generated config file |
| osSensor.config.logLevel | int | `2` | Log Verbosity  |
| osSensor.config.networking.bpf | string | `""` | Berkeley Packet Filter to apply |
| osSensor.config.networking.captureDevice | string | `""` | Device to capture from |
| osSensor.config.networking.interfaces.exclude | list | `["^veth"]` | List of Network Interfaces to exclude |
| osSensor.config.networking.interfaces.include | list | `["^eth"]` | List of Network Interfaces to include |
| osSensor.create | bool | `true` | Creates osSensor DaemonSet |
| osSensor.extraEnvs | list | `[]` | Define extra environment variables for osSensor DaemonSet |
| osSensor.image.name | string | `"darktrace/ossensor"` | Image name |
| osSensor.image.pullPolicy | string | `"Always"` | Image pullPolicy |
| osSensor.image.pullSecrets | object | `{}` | Image pullSecret |
| osSensor.image.tag | string | `"6"` | Image tag |
| osSensor.labels | object | `{}` | Labels added to the osSensor resources |
| osSensor.nodeSelector | object | `{}` | Define nodeSelector for osSensor DaemonSet |
| osSensor.resources | object | `{}` | Override resources for osSensor DaemonSet |
| osSensor.secret.create | bool | `true` | Disable if creating the secret separate from Helm Chart installation |
| osSensor.tolerations | list | `[{"operator":"Exists"}]` | Define tolerations for osSensor DaemonSet, default all tolerations |
| osSensor.windowsImage.name | string | `"darktrace/ossensor-windows"` | Image name |
| osSensor.windowsImage.pullPolicy | string | `"Always"` | Image pullPolicy |
| osSensor.windowsImage.pullSecrets | object | `{}` | Image pullSecret |
| osSensor.windowsImage.tag | string | `"6"` | Image tag |
| vSensorHmacKey | string | `""` | vSensor configured HMAC key |
| vSensorHostname | string | `""` | vSensor Hostname |
| vSensorPort | string | `"443"` | vSensor Port |
| vSensorVerifyCertificate | bool | `true` |  |
