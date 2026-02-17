---
activation: model_decision
name: infra-ops
description: "Docker, CI/CD, K8s, Terraform, cloud config. Se activa con infra, deploy, containers, IaC."
---
# Infrastructure & DevOps

## Principios
- IaC siempre (Terraform/Pulumi/CloudFormation)
- Secrets via vault/KMS, never in code
- Least privilege IAM per service
- Health checks: liveness + readiness probes
- Graceful shutdown: drain connections
- Blue-green/canary deploys for high-risk changes
- Rollback plan BEFORE deploying
- Different secrets per environment