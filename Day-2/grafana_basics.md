# 📍 Grafana Learning Roadmap

## 1. What is Grafana and Why Use It?

Grafana is an open-source analytics and visualization platform.\
It allows you to query, visualize, and alert on metrics and logs from
multiple data sources.

**Key Benefits:** - Connects to multiple backends (Prometheus, InfluxDB,
Loki, Elasticsearch, etc.) - Beautiful, customizable dashboards - Rich
alerting capabilities - User management and team collaboration -
Extensible with plugins

------------------------------------------------------------------------

## 2. Grafana Architecture

1.  **Grafana Server**
    -   Core component that serves the web UI and APIs.
    -   Written in Go.
2.  **Data Sources**
    -   Grafana doesn't store metrics; it queries external sources like:
        -   Prometheus
        -   Loki (logs)
        -   Tempo (traces)
        -   ElasticSearch
        -   MySQL/PostgreSQL
3.  **Dashboards**
    -   Visualization layer where metrics are displayed.
    -   Supports graphs, tables, heatmaps, gauges, etc.
    -   Dashboards can be shared and templated.
4.  **Alerting**
    -   Integrated alerting system.
    -   Alerts can be triggered based on queries.
    -   Notifications sent via Slack, Email, PagerDuty, Opsgenie, etc.
5.  **Plugins**
    -   Extensions for panels, data sources, and apps.
    -   Community and enterprise plugins available.

------------------------------------------------------------------------

## 3. Installation Methods

-   **Bare-metal**: Install via binaries or package managers (apt,
    yum).\
-   **Docker**: Run Grafana as a container.\
-   **Kubernetes**: Deploy with manifests or operators.\
-   **Helm**: Simplifies Grafana installation on Kubernetes.

------------------------------------------------------------------------

## 4. Grafana Configuration

-   Main configuration file: **`grafana.ini`**\
-   Configurable parameters:
    -   Server (HTTP port, root URL)
    -   Database (SQLite by default, supports MySQL/Postgres)
    -   Security (admin user/password)
    -   Alerting
    -   Authentication (LDAP, OAuth, SAML)

------------------------------------------------------------------------

## 5. Connecting Grafana to Prometheus

1.  Log in to Grafana (`http://localhost:3000`).\
2.  Add Prometheus as a data source.
    -   URL: `http://prometheus:9090`\
3.  Create a new dashboard and add a panel.\
4.  Use **PromQL** queries to visualize metrics.

------------------------------------------------------------------------

✅ Next step after this: Learn how to build advanced dashboards and
integrate Loki/Tempo for logs & traces.
