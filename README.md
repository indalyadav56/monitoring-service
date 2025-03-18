# Monitoring Service

A comprehensive monitoring stack for microservices and distributed systems, providing observability through metrics, logs, and traces.

## Overview

This project sets up a complete monitoring infrastructure using industry-standard tools for collecting and visualizing metrics, logs, and traces. It's designed to provide full observability for microservices architectures and distributed systems.

## Tech Stack

### Core Components

- **Prometheus** - Metrics collection and storage
- **Grafana** - Visualization and dashboarding
- **Loki** - Log aggregation system
- **Promtail** - Log collector for Loki
- **Jaeger** - Distributed tracing system
- **Consul** - Service discovery and configuration

### Container Orchestration

- **Docker** - Containerization platform
- **Docker Compose** - Multi-container Docker applications

## Architecture

The monitoring service consists of the following components working together:

1. **Prometheus** collects metrics from applications and infrastructure
2. **Loki** aggregates logs from various sources
3. **Promtail** ships logs to Loki
4. **Jaeger** collects and visualizes distributed traces
5. **Grafana** provides dashboards for all data sources
6. **Consul** enables service discovery and health checking

## Getting Started

### Prerequisites

- Docker and Docker Compose installed
- Git (for cloning the repository)

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd monitoring-service
   ```

2. Start the monitoring stack:
   ```bash
   docker-compose up -d
   ```

3. Access the services:
   - Grafana: http://localhost:3000 (default credentials: admin/admin)
   - Prometheus: http://localhost:9090
   - Jaeger UI: http://localhost:16686
   - Consul UI: http://localhost:8500
   - Loki: http://localhost:3100

## Configuration

### Prometheus

Prometheus is configured via `prometheus.yml`. Add your targets to the scrape_configs section.

### Loki

Loki is configured via `loki-config.yaml`. The default configuration provides a good starting point for most deployments.

### Promtail

Promtail is configured via `promtail-config.yaml`. By default, it collects logs from `/var/log/*log`.

### Grafana

Grafana comes pre-configured with Prometheus and Loki as data sources. Additional dashboards can be added through the UI or via the provisioning system.

## Development

For development purposes, you can use the `dev-compose.yml` file which provides a lighter version of the stack:

```bash
docker-compose -f dev-compose.yml up -d
```

## Examples

The `examples` directory contains sample configurations and setups for different use cases.

