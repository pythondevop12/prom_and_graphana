# 📍 Prometheus Learning Roadmap

## 3. Metrics Collection

Prometheus collects metrics primarily through its **pull-based model**,
where it scrapes data from targets that expose a `/metrics` HTTP
endpoint.

------------------------------------------------------------------------

### 🔹 How Prometheus Scrapes Metrics

-   Prometheus periodically sends HTTP GET requests to targets
    (applications, services, nodes).\
-   Each target must expose metrics in **Prometheus text-based
    exposition format**.\
-   Scraped data is stored in the **Time-Series Database (TSDB)**.\
-   Scraping frequency is controlled by the `scrape_interval` parameter
    in `prometheus.yml`.

**Example scrape configuration:**

``` yaml
scrape_configs:
  - job_name: "node"
    static_configs:
      - targets: ["localhost:9100"]
```

------------------------------------------------------------------------

### 🔹 Popular Exporters

Since not all systems natively expose metrics in Prometheus format,
exporters act as **bridges** that translate system-specific data into
Prometheus-readable metrics.

1.  **Node Exporter**
    -   Exposes hardware and OS-level metrics such as:
        -   CPU usage
        -   Memory utilization
        -   Disk I/O
        -   Network statistics\
    -   Runs on each monitored node.\
    -   Example endpoint: `http://<node_ip>:9100/metrics`
2.  **cAdvisor (Container Advisor)**
    -   Collects **container-level metrics**.\
    -   Widely used in Docker and Kubernetes environments.\
    -   Provides metrics such as:
        -   CPU & memory usage per container
        -   Disk I/O and network usage per container
    -   Endpoint: `http://<host>:8080/metrics`
3.  **Blackbox Exporter**
    -   Probes endpoints (HTTP, HTTPS, DNS, TCP, ICMP).\
    -   Useful for monitoring service availability and uptime.\
    -   Example:
        -   Check if `https://example.com` is reachable.\
    -   Configured via probe modules in `blackbox.yml`.

------------------------------------------------------------------------

### 🔹 Understanding Metric Formats (`/metrics` Endpoint)

Metrics exposed by exporters or applications follow a standard format:

-   **HELP**: Description of the metric.\
-   **TYPE**: Metric type (Counter, Gauge, Histogram, Summary).\
-   **Metric Samples**: Actual values with labels.

**Example from Node Exporter:**

``` text
# HELP node_cpu_seconds_total Seconds the CPUs spent in each mode.
# TYPE node_cpu_seconds_total counter
node_cpu_seconds_total{cpu="0",mode="user"} 12345.6
node_cpu_seconds_total{cpu="0",mode="system"} 2345.7
```

**Key Points:** - Each metric line contains: - Metric name - Labels
(key-value pairs for dimensions like CPU, mode, instance) - Value
(numeric measurement) - This makes metrics **queryable and filterable**
in PromQL.

------------------------------------------------------------------------

✅ Next step after this: Learn **PromQL** to query and analyze collected
metrics.
