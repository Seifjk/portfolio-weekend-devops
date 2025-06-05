## 11. Network Integration

### Overview
To integrate this monitoring stack with your network, you need to ensure that Grafana, Prometheus, and Node Exporter can communicate with your target systems and that your network policies allow the necessary traffic.

### Steps

1. **Identify Target Systems:**
   - List all servers, applications, or services you want to monitor.
   - Ensure these systems are accessible from the monitoring stack (e.g., via internal network, VPN, or public IP).

2. **Network Access:**
   - **Internal Network:** If the monitoring stack is on the same network, ensure firewalls allow traffic between the stack and target systems.
   - **VPN:** If the stack is behind a VPN, configure the VPN to allow access to target systems.
   - **Public IP:** If exposing services publicly, use a reverse proxy (e.g., Nginx, Traefik) with HTTPS and authentication.

3. **Firewall Rules:**
   - Allow inbound traffic to Grafana (port 3000), Prometheus (port 9090), and Node Exporter (port 9100).
   - Example for UFW:
     ```bash
     sudo ufw allow 3000/tcp  # Grafana
     sudo ufw allow 9090/tcp  # Prometheus
     sudo ufw allow 9100/tcp  # Node Exporter
     ```

4. **Prometheus Scrape Configuration:**
   - Update `prometheus-configmap.yaml` to include your target systems:
     ```yaml
     scrape_configs:
       - job_name: 'node-exporter'
         static_configs:
           - targets: ['node-exporter:9100']
       - job_name: 'your-app'
         static_configs:
           - targets: ['your-app-server:8080']
     ```

5. **Grafana Data Source:**
   - Ensure Grafana can reach Prometheus. If Prometheus is on a different network, configure Grafana to use the correct URL (e.g., `http://prometheus:9090`).

6. **Testing:**
   - Deploy the stack and verify that Grafana and Prometheus can access target systems.
   - Check Prometheus targets at [http://localhost:9090/targets](http://localhost:9090/targets) to ensure all systems are being scraped.

7. **Security:**
   - Use HTTPS and authentication for all exposed services.
   - Consider using a reverse proxy (e.g., Nginx) to manage access and SSL termination.

8. **Troubleshooting:**
   - If targets are not reachable, check network policies, firewall rules, and DNS resolution.
   - Use `curl` or `telnet` to test connectivity from the monitoring stack to target systems.

--- 