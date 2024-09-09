# Three-Tier Web Application Deployment on AWS EKS using AWS EKS, ArgoCD, Prometheus, Grafana, and Jenkins

principal://iam.googleapis.com/projects/909656124240/locations/global/workloadIdentityPools/inner-root-434608-t5.svc.id.goog/subject/ns/three-tier/sa/devops-sa


helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
helm install grafana grafana/grafana

kubectl patch svc grafana -p '{"spec": {"type": "LoadBalancer"}}'
kubectl get secret grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo