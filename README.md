
# Darktrace Helm Charts

Darktrace Helm Chart repository.

## Prerequisites

[Helm](https://helm.sh) must be installed to use the charts.

## Installing

```bash
$ helm repo add darktrace https://darktrace-com.github.io/helm-charts

$ helm search repo darktrace -l

# Basic install example
$ helm install containersensor darktrace/containersensor \
    --namespace darktrace \
    --create-namespace \
    --set vSensorHmacKey=<vSensor configured HMAC key> \
    --set vSensorHostname=<vSensor Hostname> \
    --set darktraceToken=<vSensor Pull Token>

# View chart status
$ helm status containersensor --namespace darktrace
```

## Uninstalling

```bash
$ helm uninstall containersensor --namespace darktrace
```
