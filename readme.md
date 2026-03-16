# Awesome Flyte [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Kubernetes-native workflow orchestrator for machine learning, data engineering, and analytics pipelines built on top of a strongly typed, multi-language platform.

## Contents

- [Official Resources](#official-resources)
- [SDKs and Libraries](#sdks-and-libraries)
- [Plugins](#plugins)
  - [Cloud and Data Warehouses](#cloud-and-data-warehouses)
  - [Compute Backends](#compute-backends)
  - [ML Frameworks and Tracking](#ml-frameworks-and-tracking)
  - [Data Processing and Quality](#data-processing-and-quality)
  - [Notebooks and Interactive](#notebooks-and-interactive)
  - [Storage and Serialization](#storage-and-serialization)
- [Tools](#tools)
- [Deployment](#deployment)
- [Tutorials and Examples](#tutorials-and-examples)
- [Talks and Videos](#talks-and-videos)
- [Blog Posts and Articles](#blog-posts-and-articles)
- [Companies Using Flyte](#companies-using-flyte)
- [Community](#community)

## Official Resources

- [Flyte Documentation](https://docs.flyte.org/) - Comprehensive guides covering architecture, deployment, and usage.
- [Flyte Blog](https://flyte.org/blog) - Official blog with release notes, case studies, and technical deep dives.
- [Flyte GitHub](https://github.com/flyteorg/flyte) - Main repository with core platform source code.
- [FlyteSnacks](https://github.com/flyteorg/flytesnacks) - Cookbook of practical examples and integration tutorials.
- [Flyte Conference Talks](https://github.com/flyteorg/flyte-conference-talks) - Slide decks and materials from conference presentations.
<!-- lint ignore double-link -->
- [Flyte YouTube](https://www.youtube.com/channel/UCNduEoLOToNo3nFVly-vUTQ) - Official channel with demos, community syncs, and talks.

## SDKs and Libraries

- [flytekit](https://github.com/flyteorg/flytekit) - Python SDK for authoring tasks and workflows with type-safe interfaces.
- [flyte-sdk](https://github.com/flyteorg/flyte-sdk) - Next-generation Python SDK with async/await and simplified APIs for Flyte 2.
- [flytekit-java](https://github.com/flyteorg/flytekit-java) - Java and Scala SDK for authoring workflows.
- [flyteidl](https://github.com/flyteorg/flyteidl) - Protobuf interface definitions shared across all Flyte components.
- [flytestdlib](https://github.com/flyteorg/flytestdlib) - Go standard library with shared utilities used by Flyte backend services.

## Plugins

### Cloud and Data Warehouses

- [AWS Athena](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-athena) - Run SQL queries against data in S3 using Amazon Athena.
- [AWS Batch](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-batch) - Execute tasks on AWS Batch for large-scale batch processing.
- [AWS SageMaker](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-aws-sagemaker) - Train and deploy models using Amazon SageMaker.
- [BigQuery](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-bigquery) - Run SQL queries and manage datasets in Google BigQuery.
- [Snowflake](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-snowflake) - Execute queries and orchestrate data pipelines on Snowflake.
- [Hive](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-hive) - Submit and manage Apache Hive queries.

### Compute Backends

- [Spark](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-spark) - Run PySpark and Spark jobs as native Flyte tasks.
- [Ray](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-ray) - Distribute computation across Ray clusters from within workflows.
- [Dask](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-dask) - Scale Python workloads using Dask distributed computing.
- [MPI / Kubeflow](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-kf-mpi) - Run distributed training with MPI via Kubeflow MPI Operator.
- [Kubernetes Pod](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-k8s-pod) - Run tasks as fully customizable Kubernetes pods.
- [MMCloud](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-mmcloud) - Execute tasks on MemVerge Memory Machine Cloud for cost-optimized spot instances.

### ML Frameworks and Tracking

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

### Data Processing and Quality

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

### Notebooks and Interactive

- [Papermill](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-papermill) - Execute parameterized Jupyter notebooks as Flyte tasks.
- [FlyteInteractive](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-flyteinteractive) - Attach a VS Code server to running tasks for live debugging.

### Storage and Serialization

- [Deck Standard](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-deck-standard) - Render rich HTML visualizations for task outputs in Flyte Console.
- [async-fsspec](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-data-fsspec) - Async-compatible filesystem abstraction for cloud storage backends.
- [envd](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-envd) - Build reproducible container images using envd declarative configs.
- [Memray](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-memray) - Profile memory usage of Flyte tasks using Memray.
- [Identity Aware Proxy](https://github.com/flyteorg/flytekit/tree/master/plugins/flytekit-identity-aware-proxy) - Authenticate with Google Cloud Identity Aware Proxy.

## Tools

- [flytectl](https://github.com/flyteorg/flytectl) - Cross-platform CLI for managing Flyte projects, workflows, and executions.
- [pytest-flyte](https://github.com/flyteorg/pytest-flyte) - Pytest plugin for testing Flyte tasks and workflows locally.
- [flytekit-python-template](https://github.com/flyteorg/flytekit-python-template) - Cookiecutter templates for bootstrapping new Flyte projects.
- [Airflow Provider for Flyte](https://github.com/flyteorg/airflow-provider-flyte) - Trigger and monitor Flyte executions from Apache Airflow DAGs.
- [flytecopilot](https://github.com/flyteorg/flytecopilot) - Sidecar container that handles data input/output for raw container tasks.
- [Homebrew Tap](https://github.com/flyteorg/homebrew-tap) - Install flytectl via Homebrew on macOS and Linux.

## Deployment

- [Flyte Helm Chart](https://github.com/flyteorg/flyte/tree/master/charts/flyte-core) - Production Helm chart for deploying Flyte on Kubernetes.
- [Flyte Binary](https://github.com/flyteorg/flyte/tree/master/charts/flyte-binary) - Lightweight single-binary deployment for development and small teams.
- [Flyte Sandbox](https://github.com/flyteorg/flyte/tree/master/charts/flyte-sandbox) - Local sandbox environment using a single Docker container.
- [Deployment Documentation](https://docs.flyte.org/en/latest/deployment/index.html) - Guides for deploying on AWS, GCP, and Azure.

## Tutorials and Examples

- [Getting Started](https://docs.flyte.org/en/latest/getting_started/index.html) - Official quickstart guide from installation to first workflow.
<!-- lint ignore double-link -->
- [FlyteSnacks Examples](https://flytesnacks.readthedocs.io/) - Rendered documentation of all FlyteSnacks examples with explanations.
- [FlyteLabML Projects](https://github.com/flyteorg/flytelab) - End-to-end ML projects demonstrating real-world patterns.
- [Flyte the Hard Way](https://docs.flyte.org/en/latest/community/troubleshoot.html) - Troubleshooting guide for common deployment and development issues.

## Talks and Videos

- [Flyte at KubeCon 2022](https://www.youtube.com/watch?v=erUhSbJ0RWU) - Introducing Flyte as a Kubernetes-native ML orchestrator.
- [Flyte at SciPy 2022](https://www.youtube.com/watch?v=iBBzmTT9Peg) - Building reproducible data and ML pipelines with Flyte.
- [Flyte at PyData Global 2022](https://www.youtube.com/watch?v=KdHBkaAp47Q) - From notebook to production with Flyte.
- [Flyte at PyData Seattle 2023](https://www.youtube.com/watch?v=7oQ0pXdn4gw) - Scaling ML workflows in production.
- [Flyte at SciPy 2023](https://www.youtube.com/watch?v=dJXiHkNpRs4) - Leveraging Flyte for scientific computing workflows.
- [Flyte Community Syncs](https://www.youtube.com/playlist?list=PLmQd1BBY9MWoaLIFfJYGPee_puBMzzJsr) - Monthly community meetings with feature demos and discussions.

## Blog Posts and Articles

- [Flyte vs Airflow vs Prefect vs Dagster](https://flyte.org/blog/flyte-vs-airflow-vs-prefect-vs-dagster) - Comparison of major workflow orchestration platforms.
- [Introducing Flyte: A Cloud Native Machine Learning and Data Processing Platform](https://eng.lyft.com/introducing-flyte-cloud-native-machine-learning-and-data-processing-platform-fb2bb3046a59) - Original announcement from Lyft Engineering.
- [Building a Gateway to the ML Platform](https://www.linkedin.com/blog/engineering/ml-ai/building-a-gateway-to-our-ml-platform) - How LinkedIn adopted Flyte for ML infrastructure.
- [Scaling Spotify's ML Infrastructure with Flyte](https://flyte.org/blog/spotify-case-study) - Spotify's journey to production ML with Flyte.
- [How Gojek Uses Flyte](https://flyte.org/blog/gojek-case-study) - Data platform orchestration at scale in Southeast Asia.
- [Building Reproducible ML Pipelines](https://flyte.org/blog/building-reproducible-ml-pipelines) - Patterns for deterministic, auditable workflows.
- [Mapping Tasks in Flyte](https://flyte.org/blog/flyte-map-task) - Scaling embarrassingly parallel workloads.

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
- [Recogni](https://www.recogni.com/) - Autonomous vehicle perception models.
- [LatchBio](https://latch.bio/) - Bioinformatics workflow platform built on Flyte.
- [Pachama](https://pachama.com/) - Climate tech and forest carbon monitoring.
- [Bazaarvoice](https://www.bazaarvoice.com/) - Content moderation and sentiment analysis.
- [Striveworks](https://www.striveworks.com/) - Defense and government ML operations.
- [MethaneSAT](https://www.methanesat.org/) - Satellite data processing for methane tracking.

## Community

- [Slack](https://slack.flyte.org/) - Active community workspace for questions and discussions.
- [GitHub Discussions](https://github.com/flyteorg/flyte/discussions) - Async Q&A and feature proposals.
- [Monthly Community Sync](https://docs.flyte.org/en/latest/community/index.html) - First Tuesday of every month with demos and roadmap updates.
- [Contributing Guide](https://docs.flyte.org/en/latest/community/contribute/index.html) - How to contribute to the Flyte ecosystem.
- [RFC Process](https://github.com/flyteorg/flyte/tree/master/rfc) - Request for comments on major design decisions.

## Contributing

[Contributions welcome!](contributing.md)

## Footnotes

Flyte is a [Linux Foundation AI & Data](https://lfaidata.foundation/) project.
