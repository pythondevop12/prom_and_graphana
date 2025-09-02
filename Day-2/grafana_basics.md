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
## 2. Grafana Architecture

To understand Grafana’s role, it helps to see it in the broader monitoring ecosystem where it often works alongside **Prometheus**.

![Prometheus Architecture](prometheus-architecture.svg)

### 🔹 Key Components

1. **Grafana Server**
   - Core backend service written in **Go**.
   - Provides:
     - Web-based **UI** for dashboards and configuration.
     - **HTTP API** for automation and integrations.
   - Handles authentication, authorization, and user management.

2. **Data Sources**
   - Grafana **does not store metrics by itself**.  
   - Instead, it queries data from various external systems:
     - **Prometheus** – time-series metrics.
     - **Loki** – logs aggregation.
     - **Tempo** – distributed traces.
     - **Elasticsearch** – logs & search.
     - **SQL Databases** – MySQL, PostgreSQL.
   - Each data source is configured independently.

3. **Dashboards**
   - The main visualization layer where metrics are displayed.
   - Supports multiple panel types:
     - Graphs, time-series charts
     - Tables, gauges, heatmaps, pie charts
   - Features:
     - **Templating** – dynamic dashboards with variables.
     - **Sharing** – export/import, snapshots, JSON models.

4. **Alerting**
   - Grafana has a **unified alerting system**.
   - Alerts are defined at the panel or query level.
   - Key capabilities:
     - **Rule evaluation** against metrics.
     - **Notification channels**: Slack, Email, PagerDuty, Opsgenie, Webhooks.
     - **Silencing & grouping** to reduce noise.

5. **Plugins**
   - Extend Grafana’s functionality.
   - Types:
     - **Data source plugins** (new backends).
     - **Panel plugins** (new visualization types).
     - **Apps** (bundle of dashboards, data sources, panels).
   - Community-driven and enterprise-grade plugins available.

---

✅ Grafana becomes the **visual front-end** for Prometheus and other observability tools, giving teams actionable insights from metrics, logs, and traces.


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
