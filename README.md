# ActivePieces Helm Chart Documentation

## Overview

This Helm Chart deploys the ActivePieces service on a Kubernetes cluster. This chart includes optional Redis and PostgreSQL subcharts, which are necessary for ActivePieces to function correctly.

## Prerequisites

- Helm v3.x
- Kubernetes cluster v1.18+

## Getting Started

Clone the Helm Chart repository and navigate to the chart's directory:

```bash
git clone https://github.com/avid24/activepieces-helm.git
cd activepieces-helm
```

## Configuration

The `values.yaml` file contains all the configuration options for this chart. Below are some of the key configurations:

### Image Configuration:

- `image.repository`: Specifies the ActivePieces Docker image repository.
- `image.tag`: Specifies the ActivePieces Docker image tag.
- `image.pullPolicy`: Specifies the Kubernetes image pull policy.

### Service Configuration:

- `service.type`: Specifies the Kubernetes service type.
- `service.port`: Specifies the Kubernetes service port.

### Environment Variables:

- All required environment variables for ActivePieces are configured in the `env` list.

### Redis Configuration:

- `redis.enabled`: Enable or disable Redis.
- `redis.auth.enabled`: Enable or disable Redis authentication.

### PostgreSQL Configuration:

- `postgresql.enabled`: Enable or disable PostgreSQL.
- `postgresql.auth.username`: Specifies the PostgreSQL username.
- `postgresql.auth.password`: Specifies the PostgreSQL password.

### Ingress Configuration:

- `ingress.enabled`: Enable or disable ingress controller.
- `ingress.annotations`: Additional annotations for ingress.
- `ingress.hosts`: List of hostnames to configure.
- `ingress.tls`: TLS settings for ingress.

## Installation

### Using Local Helm Chart
To install the Helm chart from the local directory, use the following command:

```bash
helm upgrade --install activepieces .
```

### Using GitHub Repository

Add the Helm repository and update it:

```bash
helm repo add activepieces https://github.com/avid24/public-Helm-charts.git
helm repo update
```

To install the Helm chart, use the following command:

```bash
helm upgrade --install activepieces activepieces/activepieces
```

## Accessing ActivePieces 

### Port-forwarding

To access ActivePieces, use the following command:
```
kubectl port-forward deployment/activepieces 8080:80
```

### Ingress

To access ActivePieces using ingress largely depends on your Kubernetes cluster. Use the ingress section in the `values.yaml` file to configure ingress.


## Uninstallation

To uninstall the Helm chart, use the following command:

```bash
helm uninstall activepieces
```

## Additional Notes

- PostgreSQL will automatically create a database named `activepieces`.
- Redis is configured without authentication by default.

For a complete list of configurable parameters, please refer to the `values.yaml` file.

## Support and Contributions

For support or to contribute to this project, please reach out to the maintainers or create a pull request.

## License

This Helm Chart is under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
