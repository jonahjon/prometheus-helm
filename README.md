# prometheus-operator-thanos

Installs [prometheus-operator](https://github.com/coreos/prometheus-operator) to create/configure/manage Prometheus clusters atop Kubernetes. This chart includes multiple components and is suitable for a variety of use-cases.

## TL;DR;

1. Edit object-store.yaml with bucket info
2. Add object-store.yaml to .gitignore once you puts keys into it
3. Edit Ingress setting on grafana/prom to Company settings
```console
$ helm install  --name thanos --namespace <MYNAMESPACE> ./prometheus-operator
```


#  Create
helm install --name thanos --namespace monitoring ./prometheus-operator

# Update
helm upgrade thanos ./prometheus-operator

# Delete
#### CRD's need to be deleted sepertley
helm delete thanos --purge
kubectl delete crd prometheuses.monitoring.coreos.com
kubectl delete crd prometheusrules.monitoring.coreos.com
kubectl delete crd servicemonitors.monitoring.coreos.com
kubectl delete crd podmonitors.monitoring.coreos.com
kubectl delete crd alertmanagers.monitoring.coreos.com



#TODO
1. Example Simple App toggleable
2. Blackbox Exporter
3. How to configure Nginx ingress correctly
4. Others?