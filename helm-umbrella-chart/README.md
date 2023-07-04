# Helm Dependencies

This example application demonstrates how an OTS (off-the-shelf) helm chart can be retrieved and pinned to a specific helm sem version from an upstream helm repository, and customized using a custom values.yaml in the private git repository.

In this example, the external-secrets application is pulled from the external-secrets helm repo, and pinned to `0.9.0`:

```yaml
dependencies:
- name: external-secrets
  version: 0.9.0
  repository: https://charts.external-secrets.io
```

A custom `values-dev.yaml` is used to customize the parameters of the `external-secrets` helm chart:

```yaml
external-secrets:
  podLabels:
    eso: dev
```

### Subchart Note
