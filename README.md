# Full Observability & Security Solution

## Overview

This project demonstrates a complete observability and security stack for a containerized web application, integrated with Prometheus, Grafana, and AWS Services.

##  Quick Start

1. Clone the repository:
	```bash
	git clone https://github.com/viateur-amalitech/Full-Observability-Security-Solution.git
	cd Full-Observability-Security-Solution
	```
2. Provision infrastructure:
	```bash
	cd infra/terraform
	terraform init && terraform apply -auto-approve
	```
3. Deploy monitoring stack locally:
	```bash
	cd monitoring
	docker compose up -d
	```
4. Access services:
	- Web App: `http://localhost:3000` (or EC2 public IP)
	- Prometheus: `http://localhost:9090`
	- Grafana: `http://localhost:3001` (admin/admin1)
	- Metrics: `http://localhost:3000/metrics`

## Documentation

- [Runbook & Setup Guide](./docs/runbook.md)
- [Implementation Report](./docs/REPORT.md)
- [Screenshots](./docs/screenshots/)


## Key Implementations

- **Metrics**: Exposed at `/metrics` using `prom-client` in the Node.js application.
- **Monitoring**: Prometheus scraping app and Node Exporter metrics.
- **Visualization**: Grafana dashboard for Latency, RPS, and Error Rates.
- **Alerting**: Prometheus/Grafana alerts for high error rates (>5%).
- **Logging**: Docker logs streamed to AWS CloudWatch.
- **Security**: AWS CloudTrail (activity auditing) and AWS GuardDuty (threat detection) enabled.
- **Compliance**: CloudTrail logs stored in encrypted S3 buckets with lifecycle policies.


## Components

- **Prometheus**: Port 9090
- **Grafana**: Port 3001 (Admin: `admin`/`admin1`)
- **Node Exporter**: Port 9100
- **Web App**: Port 3000
- 

<img width="1918" height="942" alt="image" src="https://github.com/user-attachments/assets/44bc9698-78df-4062-ab30-68a9d428dfd1" />

