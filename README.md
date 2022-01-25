# helm-chart

## Versions

### cluster-issuer
cluster-issuer 1.0.2 - http01 resolver
cluster-issuer 1.0.3 - dns01 resolver

### hello-k8s
hello-k8s 0.1.0

## Usage
Helm chart repository 

```shell
# make package
helm package .
# index repo
helm repo index --url https://rrrru.github.io/helm-chart/ .


# add repo
helm repo add rrrru https://rrrru.github.io/helm-chart/
helm repo update

# install chart
helm install rrrru/<helm chart name> --version <helm chart version>

helm install rrrru/cluster-issuer --set "email=you@yourhost.com" --version 1.0.3

helm upgrade -i -n default hello-k8s rrrru/hello-k8s --set "ingress.hosts[0].host=example.com,ingress.hosts[0].paths[0].path=/" \
    --set "ingress.tls[0].hosts={example.com}" --set "ingress.tls[0].secretName=letsencrypt-prod-hello-k8s" \
	--set "image.repository=paulbouwer/hello-kubernetes" --version 0.1.0 --dry-run

```