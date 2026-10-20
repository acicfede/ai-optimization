# AI Optimization Demo — Artifacts

This repository contains the Kubernetes/OpenShift manifests and configuration files for the **AI Optimization demo**, covering GPUaaS, AI workload management, model routing, and observability.

## Prerequisites

The following platform components are assumed to be already installed and operational:

- **OpenShift Container Platform (OCP)**.
- **Red Hat OpenShift AI (RHOAI)**.
- Required platform operators and infrastructure components, where applicable.

This repository focuses on project-specific resources and custom configurations rather than redeploying components already provided by OCP and OpenShift AI.

## Repository Structure

| Directory | Description |
|---|---|
| `gpuaas/` | GPUaaS manifests and Kueue configuration, including ResourceFlavors, queues, hardware profiles, and priority classes. |
| `smart-model-router-validated-pattern/` | Smart Model Router deployment manifests and configuration. |
| `observability/` | Observability resources, including ServiceMonitors, PrometheusRules, and Grafana dashboard ConfigMaps. |

## Configurations to Be Versioned

Project-specific configurations and custom resources must be maintained in this repository, including:

- **GPUaaS and Kueue:** queues, ResourceFlavors, hardware profiles, priority classes, and related resources.
- **MaaS and model management:** custom manifests and configuration required by the solution, including integrations and policies where applicable.
- **Smart Model Router:** application configuration, Deployment, Service, and Route.
- **Observability:** Grafana dashboards, monitoring rules, and related configuration resources.

Standard components already provided by OCP and OpenShift AI should not be duplicated in this repository unless project-specific customizations or additional resources are required.

## Security

- Do not commit passwords, access tokens, private keys, or other secrets in plaintext.
- Manage credentials through Kubernetes/OpenShift Secrets or dedicated secret-management solutions.
- Avoid hardcoding environment-specific hostnames, addresses, and parameters when these can be managed through environment-specific configuration.

## Validation and Deployment

Validate manifests with Kustomize before deployment and verify that the required platform components are available in the target environment.

Changes to this repository do not automatically apply resources to a cluster.
