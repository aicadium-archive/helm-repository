# Helm Repository

Helm repository for forked charts. This is served using the
[Github pages](https://github.com/helm/helm/blob/master/docs/chart_repository.md#github-pages-example)
method.

You can find the charts at `charts.amoy.ai`.

## Usage

Add the repository using `helm`:

```bash
helm repo add amoy https://charts.amoy.ai
```

## Packaging

```bash
helm package charts/consul charts/traefik/stable/traefik charts/vault/incubator/vault
```

Move all the tarballs to `docs`.

## Generating Index

```bash
helm repo index docs --url https://charts.amoy.ai
```
