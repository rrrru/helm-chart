# helm-chart

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
```