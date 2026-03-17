# Awesome Flyte [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Dynamic, resilient AI orchestration for building fault-tolerant workflows and agents. The most intuitive, developer-loved way to orchestrate AI in open source, now available for local execution.

## Contents

- [Official Resources](#official-resources)
- [SDKs](#sdks)
- [Flyte 2 Plugins](#flyte-2-plugins)
  - [AI and LLM](#ai-and-llm)
  - [Cloud and Data Warehouses](#cloud-and-data-warehouses)
  - [Compute Backends](#compute-backends)
  - [ML Frameworks and Tracking](#ml-frameworks-and-tracking)
  - [Data Processing](#data-processing)
- [Flyte 1 Plugins](#flyte-1-plugins)
  - [Cloud and Data Warehouses (v1)](#cloud-and-data-warehouses-v1)
  - [Compute Backends (v1)](#compute-backends-v1)
  - [ML Frameworks and Tracking (v1)](#ml-frameworks-and-tracking-v1)
  - [Data Processing and Quality (v1)](#data-processing-and-quality-v1)
  - [Notebooks and Interactive (v1)](#notebooks-and-interactive-v1)
  - [Storage and Serialization (v1)](#storage-and-serialization-v1)
- [Tools](#tools)
- [Deployment](#deployment)
- [Tutorials and Examples](#tutorials-and-examples)
- [Talks and Videos](#talks-and-videos)
- [Blog Posts and Articles](#blog-posts-and-articles)
- [Companies Using Flyte](#companies-using-flyte)
- [Community](#community)

## Official Resources

- [Flyte Documentation](https://www.union.ai/docs/flyte/) - Comprehensive guides covering architecture, deployment, and usage.
<!-- lint ignore double-link -->
- [Flyte 2 User Guide](https://www.union.ai/docs/v2/flyte/user-guide/) - Official documentation for Flyte 2 workflows and SDK.
- [Flyte Blog](https://www.union.ai/resources) - Official blog with release notes, case studies, and technical deep dives.
- [Flyte GitHub](https://github.com/flyteorg/flyte) - Monorepo with backend services, Helm charts, and interface definitions.
- [FlyteSnacks](https://github.com/flyteorg/flytesnacks) - Cookbook of practical examples and integration tutorials.
- [Flyte Conference Talks](https://github.com/flyteorg/flyte-conference-talks) - Slide decks and materials from conference presentations.
<!-- lint ignore double-link -->
- [Flyte YouTube](https://www.youtube.com/channel/UCNduEoLOToNo3nFVly-vUTQ) - Official channel with demos, community syncs, and talks.
- [Flyte 1 to 2 Migration Guide](https://www.union.ai/docs/v2/byoc/user-guide/flyte-2/) - Guide for migrating workflows from Flyte 1 to Flyte 2.

## SDKs

<!-- lint ignore double-link -->
- [flyte-sdk](https://github.com/flyteorg/flyte-sdk) - Flyte 2 Python SDK with async/await, pure Python control flow, and `flyte` CLI.
- [flytekit](https://github.com/flyteorg/flytekit) - Flyte 1 Python SDK using `@task` and `@workflow` decorators with `pyflyte` CLI.
- [flytekit-java](https://github.com/flyteorg/flytekit-java) - Java and Scala SDK for authoring workflows.

## Flyte 2 Plugins

<!-- lint ignore double-link -->
Flyte 2 plugins live in the [flyte-sdk/plugins](https://github.com/flyteorg/flyte-sdk/tree/main/plugins) directory and install via `pip install flyte[plugin-name]`.

### AI and LLM

- [OpenAI](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/openai) - Call OpenAI APIs for chat completions and embeddings within tasks.
- [Anthropic](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/anthropic) - Integrate Anthropic Claude models into Flyte workflows.
- [Gemini](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/gemini) - Use Google Gemini models for generative AI tasks.
- [vLLM](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/vllm) - Serve and run inference with large language models via vLLM.
- [SGLang](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/sglang) - Structured generation and LLM programming with SGLang.
- [Codegen](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/codegen) - Generate and execute code within Flyte tasks.
- [Human-in-the-Loop](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/hitl) - Pause workflows for human review, approval, or annotation.

### Cloud and Data Warehouses

- [BigQuery](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/bigquery) - Run SQL queries and manage datasets in Google BigQuery.
- [Snowflake](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/snowflake) - Execute queries and orchestrate data pipelines on Snowflake.
- [Databricks](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/databricks) - Submit and monitor jobs on Databricks clusters.

### Compute Backends

- [Spark](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/spark) - Run PySpark and Spark jobs as native Flyte tasks.
- [Ray](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/ray) - Distribute computation across Ray clusters from within workflows.
- [Dask](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/dask) - Scale Python workloads using Dask distributed computing.
- [PyTorch](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/pytorch) - Run distributed PyTorch training jobs.

### ML Frameworks and Tracking

- [MLflow](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/mlflow) - Track experiments and log models using MLflow.
- [Weights & Biases](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/wandb) - Log metrics, artifacts, and visualizations to W&B.

### Data Processing

- [Polars](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/polars) - Use Polars DataFrames as native Flyte types.
- [JSONL](https://github.com/flyteorg/flyte-sdk/tree/main/plugins/jsonl) - Read and write JSONL files as structured data in workflows.

## Flyte 1 Plugins

Flyte 1 plugins live in the [flytekit/plugins](https://github.com/flyteorg/flytekit/tree/master/plugins) directory and install via `pip install flytekitplugins-name`. These work with `flytekit` (v1 SDK).

### Cloud and Data Warehouses (v1)

- [AWS Athena](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-athena) - Run SQL queries against data in S3 using Amazon Athena.
- [AWS Batch](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-batch) - Execute tasks on AWS Batch for large-scale batch processing.
- [AWS SageMaker](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-sagemaker) - Train and deploy models using Amazon SageMaker.
- [BigQuery](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-bigquery) - Run SQL queries and manage datasets in Google BigQuery.
- [Snowflake](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-snowflake) - Execute queries and orchestrate data pipelines on Snowflake.
- [Hive](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-hive) - Submit and manage Apache Hive queries.

### Compute Backends (v1)

- [Spark](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-spark) - Run PySpark and Spark jobs as native Flyte tasks.
- [Ray](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-ray) - Distribute computation across Ray clusters from within workflows.
- [Dask](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-dask) - Scale Python workloads using Dask distributed computing.
- [MPI / Kubeflow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-kf-mpi) - Run distributed training with MPI via Kubeflow MPI Operator.
- [Kubernetes Pod](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-k8s-pod) - Run tasks as fully customizable Kubernetes pods.
- [MMCloud](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-mmcloud) - Execute tasks on MemVerge Memory Machine Cloud for cost-optimized spot instances.

### ML Frameworks and Tracking (v1)

- [PyTorch / Kubeflow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-kf-pytorch) - Run distributed PyTorch training with Kubeflow PyTorch Operator.
- [TensorFlow / Kubeflow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-kf-tensorflow) - Run distributed TensorFlow training with Kubeflow TF Operator.
- [Hugging Face](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-huggingface) - Integrate Hugging Face datasets and models as Flyte types.
- [MLflow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-mlflow) - Track experiments and log models using MLflow.
- [Weights & Biases](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-wandb) - Log metrics, artifacts, and visualizations to W&B.
- [Comet ML](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-comet-ml) - Track experiments and manage model metadata with Comet.
- [Neptune](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-neptune) - Log and compare ML experiments with Neptune.
- [Optuna](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-optuna) - Run hyperparameter optimization studies using Optuna.
- [ONNX PyTorch](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-onnx-pytorch) - Export and serve PyTorch models in ONNX format.
- [ONNX TensorFlow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-onnx-tensorflow) - Export and serve TensorFlow models in ONNX format.
- [ONNX scikit-learn](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-onnx-scikitlearn) - Export and serve scikit-learn models in ONNX format.

### Data Processing and Quality (v1)

- [Polars](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-polars) - Use Polars DataFrames as native Flyte types.
- [Modin](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-modin) - Accelerate Pandas workflows with Modin parallelization.
- [Vaex](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-vaex) - Handle out-of-core DataFrames with Vaex integration.
- [DuckDB](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-duckdb) - Run analytical SQL queries using embedded DuckDB.
- [Pandera](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-pandera) - Validate DataFrames at task boundaries using Pandera schemas.
- [Great Expectations](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-greatexpectations) - Add data quality checks to pipelines with Great Expectations.
- [WhyLogs](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-whylogs) - Profile datasets and detect data drift with WhyLabs.
- [DBT](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-dbt) - Orchestrate dbt models and tests as part of Flyte workflows.
- [SQLAlchemy](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-sqlalchemy) - Query any SQLAlchemy-compatible database from Flyte tasks.
- [OmegaConf](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-omegaconf) - Use OmegaConf structured configs as Flyte types.

### Notebooks and Interactive (v1)

- [Papermill](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-papermill) - Execute parameterized Jupyter notebooks as Flyte tasks.
- [FlyteInteractive](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-flyteinteractive) - Attach a VS Code server to running tasks for live debugging.

### Storage and Serialization (v1)

- [Deck Standard](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-deck-standard) - Render rich HTML visualizations for task outputs in Flyte Console.
- [envd](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-envd) - Build reproducible container images using envd declarative configs.
- [Memray](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-memray) - Profile memory usage of Flyte tasks using Memray.

## Tools

<!-- lint ignore double-link -->
- [Flyte CLI](https://github.com/flyteorg/flyte-sdk) - Built into flyte-sdk, provides `flyte run`, `flyte deploy`, and `flyte serve` commands.
- [pytest-flyte](https://github.com/flyteorg/pytest-flyte) - Pytest plugin for testing Flyte tasks and workflows locally.
- [flytekit-python-template](https://github.com/flyteorg/flytekit-python-template) - Cookiecutter templates for bootstrapping new Flyte projects.
- [Airflow Provider for Flyte](https://github.com/flyteorg/airflow-provider-flyte) - Trigger and monitor Flyte executions from Apache Airflow DAGs.
- [Homebrew Tap](https://github.com/flyteorg/homebrew-tap) - Install Flyte tools via Homebrew on macOS and Linux.

## Deployment

- [Flyte Helm Chart](https://github.com/flyteorg/flyte/tree/master/charts/flyte-core) - Production Helm chart for deploying Flyte on Kubernetes.
- [Flyte Binary](https://github.com/flyteorg/flyte/tree/master/charts/flyte-binary) - Lightweight single-binary deployment for development and small teams.
- [Flyte Sandbox](https://github.com/flyteorg/flyte/tree/master/charts/flyte-sandbox) - Local sandbox environment using a single Docker container.
- [Deployment Documentation](https://www.union.ai/docs/flyte/deployment/) - Platform deployment architecture and configuration guides.

## Tutorials and Examples

<!-- lint ignore double-link -->
- [Getting Started with Flyte 2](https://www.union.ai/docs/v2/flyte/user-guide/) - Official quickstart for the new SDK and workflow model.
- [Getting Started with Flyte 1](https://www.union.ai/docs/flyte/user-guide/) - Classic quickstart guide for flytekit-based workflows.
<!-- lint ignore double-link -->
- [Flyte Tutorials](https://www.union.ai/docs/flyte/tutorials/) - Official tutorials covering AI, ML, and data workflow patterns.
- [FlyteLabML Projects](https://github.com/flyteorg/flytelab) - End-to-end ML projects demonstrating real-world patterns.

## Talks and Videos

- [Introducing Flyte 2.0](https://www.union.ai/blog-post/introducing-flyte-2-0-dynamic-crash-proof-resource-aware-ai-orchestration) - Announcement blog post with architecture overview and motivation.

## Blog Posts and Articles

- [Spotify Cuts Quarterly Forecast Time in Half with Flyte](https://www.union.ai/case-study/to-deliver-complex-financial-reports-spotify-turns-to-flyte) - How Spotify uses Flyte to streamline financial forecasting workflows.
- [Gojek Scales ML Operations and Cuts Costs with Flyte](https://www.union.ai/case-study/to-drive-its-growing-services-gojek-looks-to-flyte) - Data platform orchestration at scale in Southeast Asia.
- [Achieving Reproducible Workflows with Flyte](https://www.union.ai/blog-post/achieving-reproducible-workflows-with-flyte) - How Flyte's versioning, typing, and containerization solve reproducibility.
- [Build Indestructible Pipelines with Flyte](https://www.union.ai/blog-post/build-indestructible-pipelines-with-flyte) - Retry mechanisms, caching, and recovery mode for resilient pipelines.

## Companies Using Flyte

- [LinkedIn](https://www.linkedin.com/) - ML platform powering recommendations and search.
- [Spotify](https://www.spotify.com/) - Audio and podcast ML pipelines.
- [Lyft](https://www.lyft.com/) - Original creators, used for pricing and ETA models.
- [Stripe](https://stripe.com/) - Fraud detection and financial ML workflows.
- [Intel](https://www.intel.com/) - Hardware optimization and AI workloads.
- [HBO / Warner Bros. Discovery](https://www.warnerbros.com/) - Content recommendation systems.
- [Gojek](https://www.gojek.com/) - On-demand services across Southeast Asia.
- [Wolt](https://wolt.com/) - Delivery optimization and demand forecasting.
- [Freenome](https://www.freenome.com/) - Genomics and cancer detection pipelines.
- [Tensordyne](https://www.tensordyne.ai/) - Autonomous vehicle perception models (formerly Recogni).
- [LatchBio](https://latch.bio/) - Bioinformatics workflow platform built on Flyte.
- [Bazaarvoice](https://www.bazaarvoice.com/) - Content moderation and sentiment analysis.
- [Striveworks](https://www.striveworks.com/) - Defense and government ML operations.
- [MethaneSAT](https://www.methanesat.org/) - Satellite data processing for methane tracking.

## Community

- [Slack](https://slack.flyte.org/) - Active community workspace for questions and discussions.
- [GitHub Discussions](https://github.com/flyteorg/flyte/discussions) - Async Q&A and feature proposals.
- [Community](https://www.union.ai/docs/flyte/community/) - How to join the community, contribute, and stay connected.
- [Contributing Guide](https://www.union.ai/docs/flyte/community/contributing-code/) - How to contribute to the Flyte ecosystem.
- [RFC Process](https://github.com/flyteorg/flyte/tree/master/rfc) - Request for comments on major design decisions.

## Contributing

[Contributions welcome!](contributing.md)

## Footnotes

Flyte is a [Linux Foundation AI & Data](https://lfaidata.foundation/) project.
