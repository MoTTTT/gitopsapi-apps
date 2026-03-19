# gitopsapi-apps

Default application catalog and GitOps templates for [gitopsapi](https://github.com/MoTTTT/gitopsapi).

This repository is the default read-only catalog source for gitopsapi installations. It is used automatically when no custom `gitops.repoUrl` is configured in the Helm chart.

## Contents

```
catalog/
  application-catalog.md    — Application definitions available for deployment

templates/
  clusters/
    cluster.json            — Template ClusterSpec for a new CAPI-managed cluster
  applications/
    application.json        — Template ApplicationSpec
  application-configs/
    application-config.json — Template ApplicationClusterConfig
```

## Usage

gitopsapi reads the catalog from this repo by default. To override with a private repo:

```yaml
# In your Helm values file
gitops:
  repoUrl: "https://github.com/<your-org>/<your-gitops-repo>.git"
```

To override the catalog source separately:

```yaml
gitops:
  catalogRepoUrl: "https://github.com/<your-org>/my-app-catalog.git"
```
