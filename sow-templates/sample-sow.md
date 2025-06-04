# sample-sow.md
*(Statement of Work Template)*

---

## 1. Introduction & Purpose

**Project Name:** ____________________________________________
**Client:** _________________________________________________
**Consultant:** ______________________________________________
**Date:** ___________________________________________________

**Purpose:**
This Statement of Work (SoW) outlines the deliverables, schedule, responsibilities, and pricing for the project described below. The goal is to ensure both parties agree on exactly what will be delivered, when, and for how much.

---

## 2. Scope of Work

**Project Overview:**
> Brief summary of the project’s objective. (e.g., “This SoW covers the setup and configuration of Grafana dashboards for ACME Corp to visualize production server metrics and configure alerts.”)

**Deliverables & Tasks:**
List each task or deliverable in detail. For every bullet, specify exactly what will be provided.

1. **Task 1: Install & Configure Grafana**
   - Install Grafana v__ on Ubuntu 20.04 (or in Docker).
   - Configure data source connection to Prometheus server at `____________`.

2. **Task 2: Create Custom Dashboards**
   - Build three dashboards:
     - Dashboard A: CPU & Memory Usage (per-node and per-container metrics)
     - Dashboard B: Application Error Rate (HTTP 5xx, 4xx, request latency)
     - Dashboard C: Network Traffic (incoming/outgoing, per-service)
   - Export each dashboard as a JSON file.

3. **Task 3: Configure Alerts**
   - Define two alert rules:
     - **Alert 1:** CPU usage > 80 % for 5 minutes → send email to devops@acme.com
     - **Alert 2:** HTTP 5xx errors > 5 % for 5 minutes → send Slack notification to #alerts

4. **Task 4: Documentation & Handover**
   - Provide a concise `README.md` describing how to:
     - Modify or add dashboards
     - Adjust alert thresholds
     - Restart/redeploy Grafana (if Dockerized)
   - Supply a PDF summary containing:
     - Dashboard JSON exports
     - Alert rule definitions
     - Sample screenshots of each dashboard

---

## 3. Timeline & Milestones

| Milestone                         | Description                                    | Due Date            |
|-----------------------------------|------------------------------------------------|---------------------|
| **Kickoff & Access Provided**     | Client grants SSH/Docker host access           | Day 0 (Date: _____) |
| **Grafana Installation Complete** | Grafana installed and basic setup verified     | Day 1, by 12:00 CET |
| **Dashboards Draft Delivered**    | Initial versions of all three dashboards       | Day 1, by 18:00 CET |
| **Alerts Configured & Tested**    | All alert rules are tested and functioning     | Day 2, by 12:00 CET |
| **Final Deliverables Submitted**  | PDF report, JSON exports, README, screenshots  | Day 2, by 17:00 CET |
| **Live Debrief Call**             | 30-minute video call to review findings         | Day 2 evening (Time) |

---

## 4. Responsibilities

**Client Responsibilities:**
- Provide SSH or Docker host access (credentials, IP allowlist) by Day 0.
- Ensure Prometheus (or chosen data source) is running and accessible.
- Designate a point of contact available for quick clarifications.

**Consultant Responsibilities:**
- Perform all tasks listed in Section 2.
- Communicate any blockers or questions within 4 business hours.
- Deliver all artifacts and conduct the debrief call as scheduled.

---

## 5. Deliverables

By the end of this engagement, the Client will receive:

1. `grafana-dashboards.json` (three exported JSON dashboards)
2. `alert-rules.yaml` (Grafana alert definitions)
3. `docker-compose.yml` (if Grafana was deployed via Docker) or install scripts
4. `README.md` explaining how to modify dashboards, adjust alerts, and redeploy Grafana
5. PDF titled “Grafana Dashboard Setup & Alert Configuration” containing:
   - Screenshots of each dashboard
   - Alert rule summaries and contact steps
   - Any notes on data source configuration
6. Recording or link to the 30-minute live debrief call

---

## 6. Pricing & Payment Terms

- **Total Fixed Fee:** € 300
  - 50 % (€ 150) due upon SoW signature
  - 50 % (€ 150) due upon final deliverable submission (Day 2)

- **Payment Method:** Bank transfer to IBAN _____________, BIC _____________ (Germany)
- **Invoice Terms:**
  - Invoice #1 (50 %) issued upon signing; due within 7 days.
  - Invoice #2 (remaining 50 %) issued upon final delivery; due within 7 days.

---

## 7. Acceptance Criteria

The work will be considered **complete and accepted** when **all** of the following are true:

- Grafana is accessible and running (either on provided host or via Docker)
- All three dashboards display real-time data from the specified data source
- Both alert rules fire correctly under test conditions and notify the correct channels
- Client confirms receipt of PDF report, JSON exports, and README
- The 30-minute debrief call occurs and client acknowledges understanding of how to maintain dashboards and alerts

---

## 8. Assumptions & Exclusions

**Assumptions:**
- Client already has a running Prometheus (or chosen) data source providing metrics.
- The target server or Docker host meets Grafana’s minimum requirements (Ubuntu 20.04 or equivalent).
- Client will grant necessary permissions and firewall rules to allow installation and data source connectivity.

**Exclusions:**
- Setting up or managing Prometheus (or alternative data source) is out of scope.
- Any additional dashboards beyond the three specified (additional dashboards will be quoted separately).
- Ongoing maintenance, upgrades, or troubleshooting outside the live debrief session.
- Any costs associated with cloud hosting, domain registration, or SSL certificates.

---

## 9. Change Management

- Any request for changes beyond the scope defined in Section 2 (e.g., adding new dashboards, modifying existing alert thresholds, or installing plugins) will require a separate change request.
- Change requests will be evaluated and quoted at € 75/hour. No work will begin on change requests without prior written approval from the Client.

---

## 10. Signatures/Authorization

By signing below, both parties agree to the terms of this Statement of Work.

**Client**
Name: __________________________________________
Signature: _____________________________________
Date: _________________________________________

**Consultant**
Name: __________________________________________
Signature: _____________________________________
Date: _________________________________________
