# ActivePieces Helm Chart Documentation

## Overview

This Helm Chart deploys the ActivePieces service on a Kubernetes cluster. This chart includes Redis and PostgreSQL as dependencies, which are necessary for ActivePieces to function correctly. 

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

- `image.repository`: ActivePieces Docker image repository.
- `image.tag`: ActivePieces Docker image tag.
- `image.pullPolicy`: Kubernetes image pull policy.

### Service Configuration:

- `service.type`: Kubernetes service type.
- `service.port`: Kubernetes service port.

### Environment Variables:

- All environment variables required for ActivePieces are configured in the `env` list.

### Redis Configuration:

- `redis.enabled`: Enable/disable Redis.
- `redis.auth.enabled`: Enable/disable Redis authentication.

### PostgreSQL Configuration:

- `postgresql.enabled`: Enable/disable PostgreSQL.
- `postgresql.auth.username`: PostgreSQL username.
- `postgresql.auth.password`: PostgreSQL password.

## Installation

To install the Helm chart, use the following command:

```bash
helm upgrade --install activepieces .
```

## Uninstallation

To uninstall the Helm chart, use the following command:

```bash
helm uninstall activepieces
```

## Additional Notes

- PostgreSQL will automatically create a database named `activepieces`.
- Redis is configured without authentication.

For a complete list of configurable parameters, please refer to the `values.yaml` file.

## Support and Contributions

For support or to contribute to this project, please reach out to the maintainers or create a pull request.

## License

This Helm Chart is under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.