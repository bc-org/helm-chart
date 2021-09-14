[![.github/workflows/release_helm.yaml](https://github.com/bc-org/helm-chart/actions/workflows/release_helm.yaml/badge.svg)](https://github.com/bc-org/helm-chart/actions/workflows/release_helm.yaml)
[![GitHub](https://img.shields.io/badge/issue_tracking-github-blue?logo=github)](https://github.com/jupyterhub/helm-chart/issues)


This repository provides Brockmann Consult Helm charts to be deployed in Kubernetes clusters. This repository stores 
its _packaged_ Helm chart in its [`gh-pages`branch](https://github.com/bc-org/helm-chart/tree/gh-pages). These packaged 
Helm charts are made available as a valid [Helm chart
repository](https://helm.sh/docs/chart_repository/) on [an automatically updated
website](https://bc-org.github.io/helm-chart/) thanks to [GitHub Pages][].
We use [chart-releaser-action](https://github.com/helm/chart-releaser-action) to
update the helm chart repository.

Currently, this repository comprises the following software charts for:

- [xcube-hub](https://github.com/bcdev/xcube-hub)

## Usage

This Helm chart repository enables you to install a xcube-hub Helm chart directly from it
into your Kubernetes cluster.

```shell
# Let helm the command line tool know about a Helm chart repository
helm repo add bc-org  https://bc-org.github.io/helm-chart
helm repo update

# Simplified example on how to install a Helm chart from a Helm chart repository
# named jupyterhub. See the Helm chart's documentation for additional details
# required.
helm install bc-org/xcube-hub --version <helm chart version>
```

In some cases you want to use this Helm chart as sub-chart. In that situation you need to
add a repository entry to your global Chart.yaml:

```yaml
dependencies:
  - name: "xcube-hub"
    version: <helm chart version>
    repository: "https://bc-org.github.io/helm-chart"
```

Then run the following command to add the xcube-hub Helm chart which will add a tared and gzipped file
(`xcube-hub-<helm chart version>.tgz`) to your charts directory:

```bash
helm dependency update
```

## Acknowledgements

This README is adapted from the [Jupyterhub](https://github.com/jupyterhub/helm-chart) helm chart README.
