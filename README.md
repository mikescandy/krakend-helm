# krakend-helm
An helm chart to deploy krakend in  a kubernetes cluster
* Installs the api-gateway system [KrakenD](http://krakend.io/)

## TL;DR;

```console
$ helm install krakend-helm
```

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release krakend-helm
```

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Upgrading an existing Release to a new major version

A major chart version change (like v1.2.3 -> v2.0.0) indicates that there is an
incompatible breaking change needing manual actions.


## Configuration

| Parameter                                 | Description                                   | Default                                                 |
|-------------------------------------------|-----------------------------------------------|---------------------------------------------------------|
| `replicas`                                | Number of nodes                               | `1`                                                     |                                                 |                                                |
| `securityContext`                         | Deployment securityContext                    | `{}`  |
| `image.repository`                        | Image repository                              | `devopsfaith/krakend`                                       |
| `image.tag`                               | Image tag                | `latest`                                                 |
| `image.pullPolicy`                        | Image pull policy                             | `IfNotPresent`                                          |
| `imagePullSecrets`                       | Image pull secrets                            | `{}`                                                    |
| `service.type`                            | Kubernetes service type                       | `ClusterIP`                                             |
| `service.port`                            | Kubernetes port where service is exposed      | `80`                                                    |
| `ingress.enabled`                         | Enables Ingress                               | `false`                                                 |
| `ingress.annotations`                     | Ingress annotations (values are templated)    | `{}`                                                    |
| `ingress.hosts`                           | Ingress accepted hostnames                    | `[]`                                                    |
| `ingress.tls`                             | Ingress TLS configuration                     | `[]`                                                    |
| `resources`                               | CPU/Memory resource requests/limits           | `{}`                                                    |
| `nodeSelector`                            | Node labels for pod assignment                | `{}`                                                    |
| `tolerations`                             | Toleration labels for pod assignment          | `[]`                                                    |
| `affinity`                                | Affinity settings for pod assignment          | `{}`                                                    |
| `annotations`                             | Deployment annotations                        | `{}`                                                    |
| `serviceAccount.annotations`              | ServiceAccount annotations                    |                                                         |
| `serviceAccount.create`                   | Create service account                        | `true`                                                  |
| `serviceAccount.name`                     | Service account name to use, when empty will be set to created account if `serviceAccount.create` is set else to `default` | `` |
| `podAnnotations`                          | Deployment                               | `{}`                                                    |
| `namespaceOverride`                       | Override the deployment namespace             | `""` (`Release.Namespace`)                              |
