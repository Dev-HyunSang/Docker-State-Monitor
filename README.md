# Docker State Monitor
This is a project to build a Simple Docker and Server Status Monitor system using `Docker-Compose.yml`  
**All systems are Docker based.**

## Systems & Technologies Used
- [Docker](https://www.docker.com/) 
- [Prometheus](https://prometheus.io/)
    - [Prometheus Node Exporter](https://github.com/prometheus/node_exporter)
    - [Prometheus PostgreSQL Exporter](https://github.com/prometheus-community/postgres_exporter)
    - [Prometheus MySQL Exporter](https://github.com/prometheus/mysqld_exporter) 
- [Google cAdvisor](https://github.com/google/cadvisor)
- [Redis](https://redis.io/)  
- [Grafana](https://grafana.com/)

## 🧭 Setting UP

### Setting up Prometheus
To set Prometheus, you can set it through `prometheus.yml`.  
You can configure basic Prometheus and Prometheus Node Exporter as shown below.

```yml
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'prometheus'

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
    - targets: ['localhost:9090']

  - job_name: 'Node-exporter'

    scrape_interval: 10s

    static_configs:
    - targets: ['localhost:9100']
```

## ⚠️ Points to watch out for
**If there is a container made with the same name and image**