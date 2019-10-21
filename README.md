#  Create
helm install --name prom-thanos --namespace monitoring ./prometheus-operator

# Update
helm upgrade prom-thanos ./prometheus-operator

# Delete
helm delete prom-thanos --purge
kubectl delete crd prometheuses.monitoring.coreos.com
kubectl delete crd prometheusrules.monitoring.coreos.com
kubectl delete crd servicemonitors.monitoring.coreos.com
kubectl delete crd podmonitors.monitoring.coreos.com
kubectl delete crd alertmanagers.monitoring.coreos.com
