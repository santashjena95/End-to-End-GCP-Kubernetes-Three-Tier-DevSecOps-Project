# Three-Tier Web Application Deployment on GCP GKE using GCP GKE, ArgoCD, Prometheus, Grafana, and Jenkins

principal://iam.googleapis.com/projects/909656124240/locations/global/workloadIdentityPools/inner-root-434608-t5.svc.id.goog/subject/ns/three-tier/sa/devops-sa


helm repo add grafana https://grafana.github.io/helm-charts

helm repo update

helm install grafana grafana/grafana

kubectl patch svc grafana -p '{"spec": {"type": "LoadBalancer"}}'

kubectl get secret grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo


helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm install prometheus prometheus-community/prometheus

helm repo update

kubectl patch svc prometheus-server -p '{"spec": {"type": "LoadBalancer"}}'

Grafana Dashboard Import: 6417, 17375