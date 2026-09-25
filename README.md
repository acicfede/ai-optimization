# AI Optimization Demo — Artifacts

Questo repository contiene i manifest e le configurazioni del demo AI Optimization (GPUaaS, MaaS, Observability).

## Struttura

| Cartella | Contenuto |
|---|---|
| `maas/` | Manifest MaaS: InferenceService, ServingRuntime, Kuadrant, Limitador, Authorino, Routes |
| `observability/` | Manifest Observability: Grafana, Prometheus, Thanos, Dashboard ConfigMaps |
| `gpuaas/` | Script e manifest GPUaaS (Red Hat Build of Kueue) |

## Cluster di riferimento

- **Cluster:** APEX (`privateailab.acic.accenture`)
- **Namespace MaaS:** `maas-demo`
- **Namespace Observability:** `mlops-team-monitoring`

## Note

- I Secret non sono inclusi per motivi di sicurezza.
- Le ConfigMap delle Grafana dashboard sono in `observability/configmap-dashboards.yaml`.
