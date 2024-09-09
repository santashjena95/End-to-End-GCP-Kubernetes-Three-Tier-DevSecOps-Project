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


## Important material for the project

GitHub Repo for Application Code and Jenkins Files: https://github.com/AmanPathak-DevOps/End-to-End-Kubernetes-Three-Tier-DevSecOps-Project/tree/master

GitHub Repo for Terraform files to create EKS Cluster: https://github.com/AmanPathak-DevOps/EKS-Terraform-GitHub-Actions

Complete Documentation for the Project: https://blog.stackademic.com/advanced-end-to-end-devsecops-kubernetes-three-tier-project-using-aws-eks-argocd-prometheus-fbbfdb956d1a

https://github.com/santashjena95/End-to-End-GCP-Kubernetes-Three-Tier-DevSecOps-Project/tree/master

https://github.com/santashjena95/GCP-GKE-Jenkins/tree/main