# Monitoring Stack Documentation

## Overview
This package provides a complete monitoring solution using Grafana, Prometheus, and Node Exporter. It enables you to monitor system metrics, visualize data with custom dashboards, and receive alerts for critical conditions. You can deploy it using Docker Compose or Kubernetes (Minikube or any K8s cluster).

---

## Contents
- `README.md`: Quick start and summary
- `docker-compose.yml`: For Docker Compose deployment
- `alerts.yaml`: Grafana alert rules (YAML)
- `dashboards/`: All dashboard JSON exports
- `k8s/`: All Kubernetes manifests

---

## 1. Deployment Options

### A. Docker Compose
1. Ensure Docker and Docker Compose are installed.
2. In the project root, run:
   ```bash
   docker-compose up -d
   ```
3. Access Grafana at [http://localhost:3000](http://localhost:3000) (default: admin/admin).
4. Access Prometheus at [http://localhost:9090](http://localhost:9090).

### B. Kubernetes (Minikube or K8s)
1. Ensure you have a running Kubernetes cluster and `kubectl` configured.
2. Apply all manifests in the `k8s/` folder:
   ```bash
   kubectl apply -f k8s/
   ```
3. Expose Grafana and Prometheus using Minikube:
   ```bash
   minikube service grafana -n monitoring
   minikube service prometheus -n monitoring
   ```
4. Default Grafana credentials: admin/admin

---

## 2. Dashboards

Dashboards are pre-built and available as JSON in the `dashboards/` folder. They are also provisioned automatically in Kubernetes.

- **CPU and Memory Dashboard:**
  - CPU usage, memory usage, load average, process count
- **Network Dashboard:**
  - Network I/O, TCP connections, network errors
- **Application Errors Dashboard:**
  - Network transmit/receive errors (can be extended for app-specific metrics)

**To import a dashboard manually:**
1. In Grafana, go to "Dashboards" > "Import".
2. Upload the JSON file or paste its contents.

---

## 3. Data Sources

- **Prometheus** is pre-configured as the default data source.
- To add more data sources (e.g., MySQL, InfluxDB):
  1. Go to "Configuration" > "Data Sources" in Grafana.
  2. Click "Add data source" and follow the prompts.

---

## 4. Alerting

- **Predefined Alerts:**
  - High CPU Usage (>80% for 5 minutes)
  - High Memory Usage (>90% for 5 minutes)
- Alert rules are in `alerts.yaml` and provisioned in Kubernetes.
- **To configure notifications (email/Slack):**
  1. In Grafana, go to "Alerting" > "Notification channels".
  2. Add your email address or Slack webhook.
  3. Assign the notification channel to the alert rules.

---

## 5. Security & Persistence

- **Change default Grafana credentials** after first login.
- **Enable HTTPS** for production (use a reverse proxy or configure TLS in Grafana).
- **Persistent storage** is configured for Grafana in Kubernetes (PVC). For Docker, map a host volume if needed.

---

## 6. Backup & Restore

### Grafana
- **Backup:**
  ```bash
  docker exec -it grafana grafana-cli admin backup
  ```
- **Restore:**
  ```bash
  docker exec -it grafana grafana-cli admin restore <backup-file>
  ```

### Prometheus
- Data is stored in a persistent volume (K8s) or Docker volume.
- Regular backups are recommended for long-term data retention.

---

## 7. Troubleshooting

- **Grafana not accessible:**
  - Check if the container/pod is running: `docker ps` or `kubectl get pods -n monitoring`
  - Check logs: `docker logs grafana` or `kubectl logs <grafana-pod> -n monitoring`
- **Prometheus not accessible:**
  - Check if the container/pod is running.
  - Check logs: `docker logs prometheus` or `kubectl logs <prometheus-pod> -n monitoring`
- **No data in dashboards:**
  - Verify Prometheus data source is configured and healthy.
  - Check if Node Exporter is running and being scraped.
  - Check Prometheus targets at [http://localhost:9090/targets](http://localhost:9090/targets)
- **Alerts not firing:**
  - Check alert rule configuration in Grafana.
  - Ensure notification channels are set up and tested.

---

## 8. Customization & Extensibility

- **Add more dashboards:**
  - Use the Grafana UI to create or import new dashboards.
  - Export as JSON and add to the `dashboards/` folder for version control.
- **Add more alerts:**
  - Use the Grafana UI or edit `alerts.yaml`.
- **Add more exporters:**
  - Deploy additional exporters (e.g., MySQL, Blackbox) and add scrape configs to Prometheus.

---

## 9. Support

For support, open an issue in your project repository or contact your service provider/freelancer.

---

## 10. License

This package is provided under the MIT License unless otherwise specified. 