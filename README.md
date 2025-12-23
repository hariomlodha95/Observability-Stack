# 🚀 Complete Observability Stack
Metrics, Logs & Traces using Prometheus, Grafana, Loki and Jaeger

## 📌 Project Objective
The objective of this project is to build a Complete Observability System that provides full visibility into an application using:
  - 📊 Metrics – Performance and resource monitoring
  - 📄 Logs – Centralized logging and log analysis
  - 🔍 Traces – End-to-end HTTP request tracing
All components are integrated using Docker Compose.

## 🛠️ Tools & Technologies
  - Python (Flask) – Sample application
  - Prometheus – Metrics collection and scraping
  - Grafana – Visualization and dashboards
  - Loki – Log aggregation system
  - Promtail – Log collector for Loki
  - Jaeger – Distributed tracing
  - Docker & Docker Compose

## 📂 Project Structure  
```
observability-stack/
├── app
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
├── docker-compose.yml
├── prometheus
│   └── prometheus.yml
├── loki
│   └── promtail-config.yaml
├── grafana
│   └── dashboards
│       ├── metrics-dashboard.json
│       └── logs-traces-dashboard.json
└── README.md
```

▶️ How to Run the Project
1️⃣ Prerequisites
  - Docker installed
  - Docker Compose installed
Verify installation:

```
docker --version
docker compose version
```

2️⃣ Start the Observability Stack
```
docker compose up -d
```

Check running containers:
```
docker compose ps
```

## 🌐 Service Access URLs
```
Python Application	  http://<server-ip>:5000
Application Metrics	  http://<server-ip>:5000/metrics
Prometheus	          http://<server-ip>:9091
Grafana	              http://<server-ip>:3000
Jaeger UI	            http://<server-ip>:16686
Loki API	            http://<server-ip>:3100
```

## 📊 Grafana Configuration
🔹 Default Login
```
Username: admin
Password: admin
```

🔹 Add Data Sources
Prometheus Data Source
```
URL: http://prometheus:9090
```

Loki Data Source
```
URL: http://loki:3100
```
Jaeger is used for tracing and can be accessed through the Explore section in Grafana or directly via the Jaeger UI.


## 📈 Metrics Monitoring
  - The application exposes metrics at the /metrics endpoint
  - Custom metric used:
```
app_requests_total
```
  - Prometheus scrapes the application successfully
  - Grafana dashboards visualize:
    - HTTP request count
    - CPU and memory usage
    - Process statistics

## 📄 Log Monitoring
  - Application logs are written to standard output
  - Promtail collects logs and sends them to Loki
  - Logs can be viewed in Grafana:

```
Grafana → Explore → Loki
```
Example log query:
```
{job="python-app"}
```

## 🔍 Distributed Tracing
  - OpenTelemetry is used for tracing HTTP requests
  - Each incoming request generates a trace span
  - Traces can be viewed in:

```
Jaeger UI → Search → Service: python-app
```
Traces provide:
  - Request latency
  - Request flow across services
  - Error analysis

## 📊 Insights Observed
 - Metrics increase in real time as requests are generated
 - Prometheus confirms the application target is UP
 - Logs are centrally available in Grafana using Loki
 - Jaeger provides full request-level visibility
 - The system enables:
    - Faster debugging
    - Performance monitoring
    - Root cause analysis

## ✅ Conclusion
This project successfully demonstrates a Complete Observability Stack using modern DevOps tools.
It provides unified visibility into application behavior through Metrics, Logs, and Traces, making monitoring and troubleshooting efficient and scalable.

## 👨‍💻 Author
-- Hariom 
-- Observability / DevOps Project
-- India 🇮🇳
