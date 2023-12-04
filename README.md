
  335  kubectl create namespace monitoring
  336  helm install node-exporter prometheus-community/prometheus-node-exporter -n monitoring
  337  helm install grafana grafana/grafana -n monitoring
  338  kubectl apply -f .
  339  kubectl get svc -n monitoring
  340  kubectl get pods -n monitoring
  341  kubectl get svc -n monitoring
  387  helm repo add kube-state-metrics
  388  helm repo add kube-state-metrics https://kubernetes.github.io/kube-state-metrics
  389  helm repo update
  390  helm install kube-state-metrics kube-state-metrics/kube-state-metrics -n monitoring
  391  kubectl get svc -n monitoring
  392  kubectl delete -f prometheus-deployment.yaml
  393  kubectl delete -f config-map.yaml
  394  kubectl apply -f config-map.yaml
  395  kubectl apply -f prometheus-deployment.yaml
