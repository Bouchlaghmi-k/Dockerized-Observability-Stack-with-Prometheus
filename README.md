# Dockerized Observability Stack with Prometheus

A complete observability and monitoring stack built using Docker Compose.  
It provides system metrics monitoring, service health checks, and alerting capabilities using the Prometheus ecosystem.

---

## 🚀 Stack Components

- **Prometheus** → Collects and queries metrics  
- **Node Exporter** → Exposes host system metrics (CPU, memory, disk)  
- **Blackbox Exporter** → Monitors external endpoints (HTTP/TCP/ICMP)  
- **Alertmanager** → Handles alerts and notifications   

---

## 🏗️ Architecture

Node Exporter ─────► Prometheus ◄──── Blackbox Exporter  
                         │  
                         ▼  
                   Alertmanager  

---

## 📁 Project Structure

monitoring-stack/  
├── docker-compose.yml  
├── prometheus/  
│   ├── prometheus.yml  
│   └── alerts/  
├── alertmanager/  
│   └── alertmanager.yml  
├── blackbox/  
│   └── blackbox.yml  
└── grafana/ (future addition)  

---

## ⚙️ How to Run

Start the stack:
```bash
docker compose up -d
````

Stop the stack:

```bash
docker compose down
```

---

## 🌐 Access Services

Prometheus → [http://localhost:9090](http://localhost:9090)
Alertmanager → [http://localhost:9093](http://localhost:9093)
Blackbox Exporter → [http://localhost:9115](http://localhost:9115)

---

## 📊 Example PromQL Queries

System health:

```promql id="q1"
up
```

CPU usage:

```promql id="q2"
rate(node_cpu_seconds_total[1m])
```

HTTP probe status:

```promql id="q3"
probe_success
```

Response time:

```promql id="q4"
probe_duration_seconds
```

---

## 🧠 What I Learned

* Docker Compose orchestration
* Observability architecture concepts
* Metrics collection and monitoring
* Service health probing
* Debugging containerized systems
* PromQL query language basics

---

## 🚀 Future Improvements

* Grafana dashboards for visualization
* Advanced alert rules (CPU, RAM, service downtime)
* Email/Telegram alert notifications
* More real-world monitoring scenarios


