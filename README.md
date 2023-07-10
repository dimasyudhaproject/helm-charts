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
