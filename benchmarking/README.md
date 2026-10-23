# LLM Benchmarking and Evaluation

This directory documents the two complementary evaluation activities used in the AI Optimization project.

## GuideLLM — performance benchmarking

GuideLLM is used to generate inference workloads and measure serving performance under configurable load. Relevant metrics include request throughput, output-token throughput, time to first token (TTFT), inter-token latency (ITL), and behavior under concurrency.

## LM Evaluation Harness — model quality

LM Evaluation Harness (`lm-eval`) is used to evaluate model quality on selected tasks and datasets. It complements performance benchmarking: quality scores and serving performance answer different questions and should be reported separately.

## Models in scope

The project materials identify these serving models as tested:

- Qwen3-32B
- GPT-OSS-20B

Confirm the exact model identifiers, revisions, serving configuration, and evaluation tasks from the original notebooks or run logs before publishing numerical comparisons.

## Reproducibility and reporting

For each run, record:

- model ID/revision and serving runtime;
- OpenShift/OpenShift AI versions and relevant GPU configuration;
- endpoint and inference parameters, without credentials;
- GuideLLM workload settings (request count or duration, concurrency, prompt/input and output-token settings);
- `lm-eval` tasks, few-shot settings, dataset/task versions, and command line;
- timestamp, run artifacts, raw output, and any errors.

Keep GuideLLM performance results separate from `lm-eval` quality results. Do not compare runs unless model, runtime, hardware, and workload/evaluation settings are sufficiently aligned.

## Current repository status

This README records the role of the tools and the models identified in project materials. The current repository archive does not include the original benchmarking notebooks, exact commands, run logs, or numerical results. Add those artifacts (after reviewing them for secrets and environment-specific details) if the benchmark needs to be reproducible from this repository.

No benchmark is executed by the validation workflow, and this documentation does not claim particular performance or quality outcomes.
