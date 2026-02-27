# Ansible Hub for Automation Configuration

## 1. Overview

Ansible Hub centralizes playbooks and roles to automate K0s, Observability, OpenVPN, and related components. The goal is to standardize deployment, make it easy to extend, and simplify troubleshooting.

## 2. Configuration Details

### 2.1 Observability
Observability is deployed via `playbooks/observability_setup.yml` and roles under `roles/observability`.

To deploy the full observability stack (Grafana, Prometheus, Loki, and Tempo), prepare the required inventory file first, then run the playbook. Example:

```bash
ansible-playbook -i inventories/dev/observability.ini playbooks/observability_setup.yml
```

#### 2.1.1 Grafana
Dashboards are provisioned automatically from `roles/observability/grafana/files/dashboards`.

#### 2.1.2 Loki
Loki collects and queries both system logs and application logs.

**Loki Dashboard for System**
System logging dashboard screenshots are stored in `images/`:

![Loki System Dashboard](images/loki_system_dashboard.png)

**Loki Dashboard for Microservices**
Microservices ([mini-ecommerce](https://github.com/NT114-Q21-Specialized-Project/mini-ecommerce-microservices)) logging dashboard:

![Loki Microservices Dashboard](images/loki_mini_ecommerce_dashboard.png)
