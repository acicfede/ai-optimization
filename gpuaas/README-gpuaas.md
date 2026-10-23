# GPU as a Service (GPUaaS)

This directory provides an example of GPU resource sharing for OpenShift AI workloads using **Kueue** and **HardwareProfiles**.

## Components

- `namespaces/`: example namespaces for inference and training.
- `resourceflavor/`: identifies eligible GPU resources for Kueue.
- `kueue/queue/`: ClusterQueues, LocalQueues and a shared cohort for quota management.
- `kueue/priorityclass/`: example priorities for inference and training workloads.
- `kueue/hardware-profiles/`: OpenShift AI HardwareProfiles linked to queues and resource requests.
- `monitoring/`: optional Kueue monitoring resources and dashboard. Managed separately from the main Kustomization.

## Prerequisites

The target cluster must have compatible versions of OpenShift AI, Kueue and the NVIDIA GPU Operator/driver stack installed. Confirm that the required CRDs are available and that GPU labels, namespaces, queue names, priorities, quotas and HardwareProfile settings match the target environment.

The included CPU, memory and GPU quotas are examples, not guaranteed capacity. GPUaaS configures scheduling and resource sharing; it does not provision GPUs or install the required operators and drivers.

## Validate and deploy

From the repository root, render the main resources without applying them:

```bash
oc kustomize gpuaas/
```

Where supported, validate against the cluster API:

```bash
oc apply --dry-run=server -k gpuaas/
```

After reviewing the rendered resources and following the approved GitOps process, deploy with:

```bash
oc apply -k gpuaas/
```

The optional `monitoring/` directory is separate. Review its permissions, ServiceMonitor settings and cluster-wide monitoring configuration with the cluster administrator before applying it.

Successful rendering does not guarantee admission or scheduling: verify Kueue status and actual GPU availability after deployment.
