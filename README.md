# grafana-loki

pre-req olarak öncelikle helm kurulması gerekiyor.

kubectl ve helm kuran scriptimden faydalanabilirsiniz.

```
curl https://raw.githubusercontent.com/alperen-selcuk/kubectl-install/main/install-kubectl-helm.sh | bash -
```

daha sonra helm reposu ekleyip values dosyasıyla birlikte install edilir.

```
helm repo add grafana https://grafana.github.io/helm-charts

helm repo update

helm install loki grafana/loki-stack --values loki-values.yaml -n loki --create-namespace
```

install sonrası password almak için, secret e bakarız

```
kubectl get secret loki-stack-grafana -oyaml
```

demo APP:

```
helm repo add sossickd https://sossickd.github.io/helm-charts/
helm repo update
helm install my-php-guest-book sossickd/php-guest-book --version 0.1.0
```
