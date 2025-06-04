# Shili Seif Eddine – DevOps/SRE Freelancer

**Availability**
• Weeknights (Mon – Thu) 20:00 – 22:00 CET (small tasks, quick fixes)
• Weekends (Fri 18:00 – Sun 18:00 CET) (larger jobs accepted)

---

## Services & Pricing

1. **Grafana Dashboard Setup & Tuning** – € 300 (4 – 5 hours)
   - Install/configure Grafana on your existing server or in Docker
   - Connect one data source (e.g., Prometheus, MySQL, etc.)
   - Build 3 custom dashboards (e.g., CPU/Memory usage, application error rate, network traffic)
   - Configure 2 alerts (email/Slack) for critical thresholds (e.g., “CPU > 80 % for 5 min,” “Error rate > 5 % for 5 min”)
   - Deliverables: JSON exports of dashboards, `docker-compose.yml` (or install script), alert definitions, concise “how-to” README

2. **Kubernetes Manifest Audit & Optimization** – € 200 (3 hours)
   - Review up to 10 existing Kubernetes YAML or Helm manifests
   - Identify missing resource requests/limits, absent liveness/readiness probes, suboptimal replica counts, and basic security gaps (e.g., containers running as root)
   - Provide a 1-page PDF with 5 – 7 actionable recommendations (e.g., “Add `resources.requests/limits`,” “Insert `readinessProbe` on port 8080,” “Enforce `securityContext.runAsNonRoot: true`,” “Implement NetworkPolicy to restrict cluster traffic”)
   - 30-minute video call to walk through findings and explain each recommendation

3. **Jenkins Pipeline Build & Integration** – € 250 (4 hours)
   - Install/configure Jenkins (assumes Docker or an existing VM)
   - Create a `Jenkinsfile` to:
     1. Checkout your Git repository on every commit
     2. Run unit tests or build commands
     3. Build a Docker image (if applicable)
     4. Push the image to Docker Hub or a private registry
   - Provide two reusable example `Jenkinsfile`s and necessary configuration snippets
   - Deliverables: Jenkins setup instructions, pipeline scripts, concise README detailing how to extend

4. **Terraform + Ansible Starter Pack** – € 300 (5 hours)
   - **Terraform**: Write `main.tf` (and any `variables.tf`/`outputs.tf`) to provision one Ubuntu VM on AWS, DigitalOcean, or another cloud of your choice (with security group and SSH key)
   - **Ansible**: Create an `inventory.ini` and `site.yml` that:
     - Connects over SSH to the newly created VM
     - Installs Docker, Git, and nginx (or two-to-three packages of your choice)
   - Provide a “how-to” guide:
     ```
     terraform init
     terraform apply
     ansible-playbook -i inventory.ini site.yml
     ```
   - Deliverables: All Terraform files, `site.yml`, `inventory.ini`, and a README showing exactly how to run and customize

---

### Add-On Services

- **Kubernetes Basic Security Hardening** – € 150 (2 hours)
  • Add `securityContext.runAsNonRoot: true` and/or `allowPrivilegeEscalation: false` to Pod specs
  • Define resource requests/limits (`requests: cpu/memory`, `limits: cpu/memory`)
  • Create a NetworkPolicy to restrict pod-to-pod traffic on specific ports
  • Deliverables: Hardened YAML manifests, 1-page PDF with change summary and rationale

- **Jenkins Security Hardening** – € 150 (2 hours)
  • Disable anonymous read access and enable matrix-based security in Jenkins
  • Create separate roles (e.g., read-only developers vs. full admins) via Role-Strategy Plugin
  • Configure HTTPS/TLS for Jenkins (self-signed or Let’s Encrypt)
  • Deliverables: PDF with screenshots of security settings, sample `jenkins.yaml` config snippets

- **Terraform + Ansible Security Enhancements** – € 100 (2 hours)
  • Restrict cloud security group to SSH (port 22) from client IP only, open ports 80/443 for HTTP/HTTPS
  • Use Ansible to install and configure UFW on Ubuntu:
    ```
    ufw default deny incoming
    ufw default allow outgoing
    ufw allow ssh
    ufw allow 80
    ufw allow 443
    ufw enable
    ```
  • Enforce SSH key-only authentication (`PasswordAuthentication no` in `/etc/ssh/sshd_config`)
  • Deliverables: Updated Terraform files, enhanced Ansible playbook (`site.yml`), 1-page security PDF

---

## Portfolio & Proof

- **Grafana Demo Dashboards**
  GitHub: https://github.com/YourName/grafana-demo-dashboards
  • Example of a Grafana install in Docker, three dashboards exported as JSON, and alert rules. Screenshots included.

- **Kubernetes Audit Demo**
  GitHub: https://github.com/YourName/k8s-audit-demo
  • “Before” and “after” YAML manifests illustrating resource limits, probes, and securityContext. PDF report with 7 recommendations.

- **Jenkins Pipeline Demo**
  GitHub: https://github.com/YourName/jenkins-pipeline-demo
  • Sample “Hello World” Node.js app, `Jenkinsfile` that builds/tests/pushes a Docker image. Log screenshots show successful builds.

- **Terraform + Ansible Demo**
  GitHub: https://github.com/YourName/terraform-ansible-demo
  • `main.tf` for provisioning a DigitalOcean droplet, `site.yml` to install Docker and nginx. Final screenshot: “Welcome to nginx!” in a browser.

> *“Shili delivered our Grafana dashboards in just one weekend. Clear instructions, fantastic support—highly recommended!”*
> — John D., SaaS Startup CTO

---

## SoW & SLA Templates

Inside the `sow-templates/` folder you’ll find two files:

1. **`sample-sow.md`** (Statement of Work template)
2. **`sample-sla.md`** (Service Level Agreement template)

### 1. `sample-sow.md` (Statement of Work)

The SoW outlines exactly **what will be done**, **who is responsible**, **when**, and **for how much**. A typical SoW includes:

1. **Introduction & Purpose**
   - Brief overview of the project (“This SoW covers the setup of a Grafana Dashboard for ACME Corp, to provide real-time metrics and alerts for production servers.”)

2. **Scope of Work**
   - Detailed bullet points of every deliverable.
     Example:
     - “Install Grafana v9.x on Ubuntu 20.04 (or Docker).”
     - “Connect Grafana to an existing Prometheus data source.”
     - “Create three dashboards: CPU/Memory Usage, Application Error Rate, Network Traffic.”
     - “Configure two alert rules (email + Slack) for CPU > 80 % and HTTP 5xx > 5 % over 5 min.”
     - “Provide a PDF report listing dashboard JSON exports, alert definitions, and a 1-page usage guide.”

3. **Timeline & Milestones**
   - Exact dates for each milestone.
     Example:
     - “SoW signed by Day 0.”
     - “Day 1 (within 24 hours of kickoff): Grafana installation completed. Draft dashboards created.”
     - “Day 2 (by 17:00 CET): Final dashboards delivered, alerts tested, PDF report sent.”
     - “Day 2 evening: Live debrief call (30 minutes).”

4. **Responsibilities**
   - **Client responsibilities**: e.g., “Provide SSH access to a server or Docker host by Day 0.”
   - **Consultant responsibilities**: e.g., “Install/configure Grafana, build dashboards, test alerts, deliver PDF.”

5. **Deliverables**
   - List of tangible outputs the client will receive.
     Example:
     - “`grafana-dashboards.json` (three dashboard exports)”
     - “`alert-rules.yaml` (Grafana alert definitions)”
     - “`docker-compose.yml` (if installed via Docker)”
     - “`README.md` (how to modify dashboards and alerts)”
     - “30-minute recorded debrief session (video link)”

6. **Pricing & Payment Terms**
   - Total fixed fee (e.g., “€ 300”)
   - Payment schedule (e.g., “50 % upfront, 50 % upon final delivery”; or “100 % on delivery”)
   - Accepted payment methods and invoicing details.

7. **Acceptance Criteria**
   - Clear conditions for when the work is considered “complete” and “accepted.”
     Example:
     - “Grafana dashboards are viewable and updating with current metrics.”
     - “Alerts fire correctly under test conditions.”
     - “Client confirms receipt of PDF report and understands how to edit/extend dashboards.”

8. **Assumptions & Exclusions**
   - State anything you will **not** do.
     Example:
     - “Out of scope: Setting up Prometheus itself (assumes Prometheus is already running).”
     - “Out of scope: AWS account fees or server hosting costs.”

9. **Change Management**
   - How to handle additional work if requirements change.
     Example:
     - “Any request for additional dashboards or data sources beyond the three specified will be quoted separately at €75/hour.”

10. **Signatures/Authorization**
    - Space for client signature, date, and consultant signature, date.

---

### 2. `sample-sla.md` (Service Level Agreement)

An SLA defines expected performance levels and support commitments. Typical sections:

1. **Parties & Term**
   - Identify “Service Provider” (you) and “Client” (their company).
   - Effective date and duration (e.g., 12 months from signature).

2. **Services Covered**
   - Brief summary of what services the SLA applies to.
     Example: “This SLA covers monitoring and alert support for the Grafana dashboards installed under SoW#1234.”

3. **Performance Metrics & Targets**
   - Uptime/Availability targets.
     Example: “Grafana dashboards shall be available (responding to HTTP requests) 99.5 % of the time, measured monthly.”
   - Response times for incidents.
     Example: “For Severity 1 issues (dashboard unreachable), response within 2 hours on weekends; Severity 2 issues (alerts misfiring) response within 4 hours.”

4. **Support Hours & Contact Methods**
   - When you are “on duty” and the best way to reach you.
     Example: “Support window: Fri 18:00 – Sun 18:00 CET. Email and Slack DMs monitored during these hours.”

5. **Maintenance & Planned Downtime**
   - How you’ll notify them of upgrades or brief interruptions.
     Example: “Provider will give 48 hours’ notice for any planned maintenance.”

6. **Escalation Procedures**
   - If the initial contact doesn’t respond in the expected window, how the client can escalate.
     Example: “If no response within 2 hours, call support hotline at +49 160 1234567.”

7. **Reporting & Metrics**
   - Frequency of availability reports or post-incident reviews.
     Example: “Monthly availability report shared via email on the 5th of each month.”

8. **Penalties & Remedies**
   - If targets are not met, what happens.
     Example: “If monthly uptime drops below 99.5 %, client is entitled to a 10 % credit on that month’s fee.”

9. **Exclusions**
   - Situations outside your control (force majeure, client network issues, third-party outages).

10. **Termination**
    - How either party can end the SLA if service isn’t meeting expectations (e.g., 30 days’ written notice).

11. **Signatures**
    - Space for client and provider to sign and date.

---

## Contact & Booking

- **Upwork**: https://www.upwork.com/fl/your-profile
- **Malt**: https://www.malt.de/profile/your-id
- **Email**: devops@example.com
- **LinkedIn**: https://www.linkedin.com/in/yourprofile

Feel free to email me with project details or book a 15-minute discovery call at https://calendly.com/your-calendly. I’ll reply within 24 hours.

---
