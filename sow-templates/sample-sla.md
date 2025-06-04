# sample-sla.md
*(Service Level Agreement Template)*

---

## 1. Parties & Term

**Service Provider:**
Name: __________________________________________
Address: ________________________________________

**Client:**
Name: __________________________________________
Address: ________________________________________

**Effective Date:** _______________
**Term Duration:** 12 months (from Effective Date)

---

## 2. Services Covered

This Service Level Agreement (SLA) applies to the following services provided by the Service Provider under the associated SoW numbers:
- Grafana Dashboard Monitoring & Alert Support (SoW #______)
- Kubernetes Manifest Audit & Optimization (SoW #______)
- Jenkins Pipeline Support (SoW #______ )

---

## 3. Performance Metrics & Targets

**3.1 Availability/Uptime**
- The Service Provider guarantees 99.5 % availability of the Grafana dashboards **measured monthly**.
- **Availability Calculation:**
  \[(Total minutes in month – Downtime minutes) / (Total minutes in month)\] × 100 %

**3.2 Incident Response Times**
| Severity | Description                                    | Response Time        | Resolution Target     |
|----------|------------------------------------------------|----------------------|-----------------------|
| **S1**   | Dashboard unreachable (no data for > 15 min)   | 2 hours (weekends)   | 6 hours (weekends)    |
|          |                                                | 4 hours (weekdays)   | 12 hours (weekdays)   |
| **S2**   | Alerts misfiring or false positives/negatives  | 4 hours (weekends)   | 12 hours (weekends)   |
|          |                                                | 8 hours (weekdays)   | 24 hours (weekdays)   |
| **S3**   | Minor issues (UI tweaks, minor config changes) | 1 business day       | 3 business days       |

---

## 4. Support Hours & Contact Methods

**4.1 Support Hours**
- **Weekdays:** Mon–Thu, 20:00 – 22:00 CET (quick fixes only)
- **Weekends:** Fri 18:00 – Sun 18:00 CET (all covered services)

**4.2 Contact Methods**
- **Email Support:** devops@example.com (monitored continuously during support hours)
- **Slack Channel:** #devops-support (responded to within SLA response times)
- **Emergency Phone:** +49 160 1234567 (only for Severity 1 issues if no other method works)

---

## 5. Maintenance & Planned Downtime

- Service Provider will provide at least **48 hours’ notice** for any planned maintenance that will cause more than 15 minutes of downtime.
- Planned maintenance windows will be scheduled between Fridays 18:00 and Sundays 06:00 CET, unless otherwise agreed.

---

## 6. Escalation Procedures

If the Service Provider fails to respond within the times specified in Section 3.2, the Client may escalate as follows:

1. **Primary Contact:** Email → devops@example.com
2. **Secondary Contact:** Slack DM to @ShiliSeifEddine
3. **Tertiary Contact (Emergency):** Call +49 160 1234567

If there is no response within the designated response time for the given severity, the Client may proceed to the next escalation level.

---

## 7. Reporting & Metrics

- A **monthly availability report** will be sent by the 5th calendar day of each month, containing:
  - Total uptime percentage for Grafana dashboards
  - Number of incidents by severity
  - Resolution times for each incident
  - Planned vs. unplanned downtime

- A **post-incident report** will be provided within 24 hours after any Severity 1 incident, outlining:
  - Incident cause
  - Steps taken to resolve
  - Action items to prevent recurrence

---

## 8. Penalties & Remedies

- If the monthly uptime for Grafana dashboards falls below 99.5 %, the Client is entitled to a **10 % service credit** on that month’s support fee.
- If response times exceed the targets for Severity 1 issues more than twice in a calendar quarter, the Client is entitled to a **15 % service credit** for that quarter’s support fees.

Service credits will be applied to the next invoice following the month or quarter in which the SLA breach occurred.

---

## 9. Exclusions

This SLA does **not** apply to:
- Downtime caused by the Client’s network, data center, or Internet Service Provider.
- Incidents resulting from changes made by the Client without prior written approval.
- Force majeure events (natural disasters, acts of war, major Internet backbone outages).
- Planned downtime (with 48-hour notice) and maintenance agreed upon in writing.

---

## 10. Termination

Either party may terminate this SLA with **30 days’ written notice** if the other party:
- Materially breaches any term of this SLA and fails to remedy within 15 days of written notice.
- Becomes insolvent, files for bankruptcy, or ceases operations.

Upon termination, all outstanding service credits will be applied, and any fees paid for the current month or quarter will not be refunded.

---

## 11. Signatures

By signing below, both parties agree to the terms of this Service Level Agreement.

**Client**
Name: _________________________________________
Signature: ____________________________________
Date: ________________________________________

**Service Provider**
Name: _________________________________________
Signature: ____________________________________
Date: ________________________________________
