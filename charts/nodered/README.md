# node-red

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: 2.1.4](https://img.shields.io/badge/AppVersion-2.1.4-informational?style=flat-square)

Node-RED is low-code programming for event-driven applications

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/naimo84/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/node-red/node-red-docker>
* <https://github.com/naimo84/helm-charts/tree/master/charts/node-red>

## Requirements

Kubernetes: `>=1.16.0-0`

## TL;DR

```console
helm repo add naimo84 https://naimo84.github.io/helm-charts/
helm repo update
helm install node-red naimo84/node-red
```

## Installing the Chart

To install the chart with the release name `node-red`

```console
helm install node-red naimo84/node-red
```

## Uninstalling the Chart

To uninstall the `node-red` deployment

```console
helm uninstall node-red
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install node-red \
  --set env.TZ="America/New York" \
    naimo84/node-red
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install node-red naimo84/node-red -f values.yaml
```

## Custom configuration

N/A

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [image docs](https://nodered.org/docs/getting-started/docker) for more details. |
| env.FLOWS | string | `"flows.json"` | Location of the flows configuration file. If you set `FLOWS: ""` then the flow file can be set via the `flowFile` property in the `settings.js` file. |
| env.NODE_OPTIONS | string | `nil` | Node.js runtime arguments |
| env.NODE_RED_ENABLE_PROJECTS | string | `nil` | Setting to `true` starts Node-RED with the projects feature enabled |
| env.NODE_RED_ENABLE_SAFE_MODE | string | `nil` | Setting to `true` starts Node-RED in safe (not running) mode |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"nodered/node-red"` | image repository |
| image.tag | string | `"2.1.4"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |
