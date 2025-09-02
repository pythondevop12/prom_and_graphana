# 📍 Prometheus Learning Roadmap

## 1. Foundations of Monitoring & Observability

Before diving into Prometheus, it's important to build a strong
foundation in monitoring and observability concepts.

### 🔹 Monitoring vs. Observability

-   **Monitoring**: Collecting predefined metrics to check system health
    and performance. It answers the question *"Is my system working?"*.
-   **Observability**: A broader approach that allows you to ask *"Why
    is my system not working?"*. It focuses on gaining deep insights
    into internal states from outputs.

### 🔹 Three Pillars of Observability

1.  **Metrics** -- Numerical data points that represent system behavior
    over time (e.g., CPU usage, request latency).
2.  **Logs** -- Event records providing detailed information about
    system activities.
3.  **Traces** -- Show the path of a request through distributed
    systems, helping debug bottlenecks and errors.

### 🔹 Types of Metrics in Prometheus

-   **Counter**: A cumulative metric that only increases (e.g., number
    of requests served).
-   **Gauge**: A metric that goes up and down (e.g., temperature, memory
    usage).
-   **Histogram**: Samples observations (e.g., request duration) into
    configurable buckets and counts occurrences.
-   **Summary**: Similar to a histogram but provides quantiles (e.g.,
    95th percentile latency).

### 🔹 Time-Series Data Concepts

-   Data points are stored as **time-series** (value + timestamp).
-   Each time-series is uniquely identified by a metric name and a set
    of labels.
-   Prometheus uses its own **TSDB (Time Series Database)** to store and
    query metrics efficiently.

------------------------------------------------------------------------

✅ Next step after this foundation: Learn Prometheus Architecture and
Core Concepts.
