# Prometheus and Grafana: How They Work Together

## Integration Overview
Prometheus is responsible for **collecting and storing metrics**, while Grafana is used to **visualize these metrics** in dashboards.

- **Prometheus Role**: Scrapes metrics from applications, services, and infrastructure.
- **Grafana Role**: Connects to Prometheus as a data source and visualizes the data.

## Workflow
1. Applications expose metrics (e.g., CPU usage, memory usage, HTTP requests).
2. Prometheus scrapes these metrics at defined intervals.
3. Data is stored in Prometheus' time-series database.
4. Grafana queries Prometheus using **PromQL**.
5. Grafana displays metrics in interactive dashboards for analysis.

## Example Architecture
```mermaid
graph TD
    A[Application / Service] -->|Exposes Metrics| B[Prometheus]
    B -->|Stores Time-Series Data| C[Prometheus DB]
    C -->|Queries with PromQL| D[Grafana]
    D -->|Dashboards| E[Users]
