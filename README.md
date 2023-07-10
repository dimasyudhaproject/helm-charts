# Helm Chart

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/helm/charts)](https://github.com/dimasyudhatech/Helm-charts/releases/)
[![Docker Pulls](https://img.shields.io/docker/pulls/dimasyudhatech/server?color=green)](https://hub.docker.com/repository/docker/dimasyudhatech/server)

This Helm chart deploys a highly available, auto-scaling web server application on a Kubernetes cluster using the Helm package manager. It also sets up necessary configurations for DNS and HTTPS with Let's Encrypt for secure communication.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Quickstart](#quickstart)
- [Configuration](#configuration)
- [Production Considerations](#production-considerations)
- [Running Tests](#running-tests)
- [Contributing](#contributing)
- [License](#license)
- [Contact Information](#contact-information)

## Prerequisites

- Kubernetes 1.14+
- Helm 3.0+

## Quickstart

```bash
# Clone the repository
git clone https://github.com/dimasyudhatech/Helm-charts.git

# Install the Helm Chart
helm install server ./chart
```

## Configuration

The following table lists the configurable parameters of the chart and their default values.

| Parameter                                      | Description                                                  | Default              |
|------------------------------------------------|--------------------------------------------------------------|----------------------|
| `image.repository`                             | Server image repository                                      | `nginx`              |
| `image.tag`                                    | Server image tag                                             | `latest`             |
| `image.pullPolicy`                             | Server image pull policy                                     | `IfNotPresent`       |
| `replicaCount`                                 | Desired number of server pods                                | `1`                  |
| `autoscaling.enabled`                          | Enables Kubernetes horizontal pod autoscaler                 | `false`              |
| `autoscaling.minReplicas`                      | Minimum number of server pods                                | `1`                  |
| `autoscaling.maxReplicas`                      | Maximum number of server pods                                | `100`                |
| `autoscaling.targetCPUUtilizationPercentage`   | Target CPU utilization for autoscaling                       | `80`                 |
| `ingress.enabled`                              | Enables Ingress for server                                   | `false`              |
| `ingress.annotations`                          | Ingress annotations for additional configuration             | `{}`                 |
| `ingress.hosts`                                | Ingress accepted hostnames                                   | `chart-example.local`|
| `ingress.tls`                                  | Ingress TLS configuration                                    | `[]`                 |

## Production Considerations

For a production environment, consider adjusting the following parameters:

| Parameter                                   | Consideration                                                                               |
|---------------------------------------------|---------------------------------------------------------------------------------------------|
| `image.tag`                                 | Use a specific version of your server image, not `latest`.                                  |
| `replicaCount`                              | Increase this for more redundancy.                                                          |
| `autoscaling.minReplicas`                   | Increase this based on your load requirements.                                              |
| `autoscaling.maxReplicas`                   | Increase this based on your load requirements.                                              |
| `autoscaling.targetCPUUtilizationPercentage`| Adjust according to the workload. A higher percentage means the autoscaler will kick in later|
| `ingress.enabled`                           | Should be set to `true` to enable exposure of the service outside of the cluster.            |