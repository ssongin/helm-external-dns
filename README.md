
# Helm ExternalDNS

Helm chart that deploys [ExternalDNS](https://github.com/kubernetes-sigs/external-dns) and manages its credentials using [External Secrets Operator](https://external-secrets.io/).

## Installation

```bash
helm upgrade --install external-dns \
  oci://ghcr.io/ssongin/helm-external-dns \
  --version {chart_version} \
  --namespace external-dns \
  --create-namespace
```

## Configuration

Configure ExternalDNS and the `ExternalSecret` in `values.yaml`.

Set `externalSecret.data` to specify which secrets to retrieve from your secret store.

## CI/CD

GitHub Actions validates the chart on pull requests and publishes it to GitHub Container Registry (GHCR) when changes are merged into `master`.
