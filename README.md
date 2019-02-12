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

## Packaging and indexing

```bash
git branch -D gh-pages
helm package charts/consul charts/traefik/stable/traefik charts/vault/incubator/vault
git checkout --force --orphan gh-pages
helm repo index ./ --url https://charts.amoy.ai

rm -rf charts .gitmodules LICENSE README.md

git add .
git commit -m "Update index"

git push -u origin gh-pages --force
```
