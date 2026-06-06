1. EKS (Elastic Kubernetes Service)
   
| Task               | Command                                                                   |
| ------------------ | ------------------------------------------------------------------------- |
| Configure AWS CLI  | `aws configure`                                                           |
| Create EKS Cluster | `eksctl create cluster --name demo-cluster --region ap-south-1 --nodes 2` |
| List Clusters      | `aws eks list-clusters`                                                   |
| Update Kubeconfig  | `aws eks update-kubeconfig --region ap-south-1 --name demo-cluster`       |
| Get Nodes          | `kubectl get nodes`                                                       |
| Delete Cluster     | `eksctl delete cluster --name demo-cluster`                               |


2. Basic Kubernetes Commands

| Task          | Command                                 |
| ------------- | --------------------------------------- |
| Cluster Info  | `kubectl cluster-info`                  |
| Get Nodes     | `kubectl get nodes`                     |
| Get Pods      | `kubectl get pods`                      |
| All Resources | `kubectl get all`                       |
| Describe Pod  | `kubectl describe pod podname`          |
| Pod Logs      | `kubectl logs podname`                  |
| Exec into Pod | `kubectl exec -it podname -- /bin/bash` |
| Delete Pod    | `kubectl delete pod podname`            |

3. YAML Validation
| Task          | Command                                                                  |
| ------------- | ------------------------------------------------------------------------ |
| Dry Run       | `kubectl apply -f deploy.yml --dry-run=client`                           |
| Generate YAML | `kubectl create deployment nginx --image=nginx --dry-run=client -o yaml` |
| Apply YAML    | `kubectl apply -f deploy.yml`                                            |
| Delete YAML   | `kubectl delete -f deploy.yml`                                           |

4. Deployment Commands
| Task              | Command                                         |
| ----------------- | ----------------------------------------------- |
| Create Deployment | `kubectl create deployment nginx --image=nginx` |
| Get Deployments   | `kubectl get deploy`                            |
| Scale Deployment  | `kubectl scale deployment nginx --replicas=5`   |
| Edit Deployment   | `kubectl edit deployment nginx`                 |
| Delete Deployment | `kubectl delete deployment nginx`               |

5. Service Commands
| Service Type     | Command                                                         |
| ---------------- | --------------------------------------------------------------- |
| ClusterIP        | `kubectl expose deployment nginx --port=80 --type=ClusterIP`    |
| NodePort         | `kubectl expose deployment nginx --port=80 --type=NodePort`     |
| LoadBalancer     | `kubectl expose deployment nginx --port=80 --type=LoadBalancer` |
| Get Services     | `kubectl get svc`                                               |
| Describe Service | `kubectl describe svc nginx`                                    |
6. Namespace Commands
| Task             | Command                                                |
| ---------------- | ------------------------------------------------------ |
| Create Namespace | `kubectl create ns dev`                                |
| Get Namespace    | `kubectl get ns`                                       |
| Delete Namespace | `kubectl delete ns dev`                                |
| Switch Namespace | `kubectl config set-context --current --namespace=dev` |
7. Scaling Commands
Horizontal Scaling
| Task           | Command                                                                |
| -------------- | ---------------------------------------------------------------------- |
| Scale Replicas | `kubectl scale deployment nginx --replicas=5`                          |
| Create HPA     | `kubectl autoscale deployment nginx --cpu-percent=50 --min=2 --max=10` |
| Get HPA        | `kubectl get hpa`                                                      |
Vertical Scaling
| Task           | Command                         |
| -------------- | ------------------------------- |
| Edit Resources | `kubectl edit deployment nginx` |
| View Resources | `kubectl describe pod podname`  |
Cluster Scaling (EKS)
| Task               | Command                  |
| ------------------ | ------------------------ |
| Cluster Autoscaler | Via Helm                 |
| Increase Nodes     | `eksctl scale nodegroup` |

8. Rollout Commands
| Task              | Command                                                 |
| ----------------- | ------------------------------------------------------- |
| Rollout Status    | `kubectl rollout status deployment/nginx`               |
| Rollout History   | `kubectl rollout history deployment/nginx`              |
| Rollout Restart   | `kubectl rollout restart deployment/nginx`              |
| Rollback          | `kubectl rollout undo deployment/nginx`                 |
| Rollback Revision | `kubectl rollout undo deployment/nginx --to-revision=2` |
9. DaemonSet
| Task        | Command                          |
| ----------- | -------------------------------- |
| Create DS   | `kubectl apply -f daemonset.yml` |
| Get DS      | `kubectl get ds`                 |
| Describe DS | `kubectl describe ds fluentd`    |

10. StatefulSet
| Task               | Command                            |
| ------------------ | ---------------------------------- |
| Create StatefulSet | `kubectl apply -f statefulset.yml` |
| Get StatefulSet    | `kubectl get sts`                  |
| Delete StatefulSet | `kubectl delete sts mysql`         |

11. Jobs & CronJobs
| Task           | Command                        |
| -------------- | ------------------------------ |
| Create Job     | `kubectl apply -f job.yml`     |
| Get Jobs       | `kubectl get jobs`             |
| Create CronJob | `kubectl apply -f cronjob.yml` |
| Get CronJobs   | `kubectl get cronjobs`         |

12. ConfigMaps
| Task               | Command                                                        |
| ------------------ | -------------------------------------------------------------- |
| Create ConfigMap   | `kubectl create configmap app-config --from-literal=name=test` |
| Get ConfigMap      | `kubectl get cm`                                               |
| Describe ConfigMap | `kubectl describe cm app-config`                               |
13. Secrets
| Task          | Command                                                                |
| ------------- | ---------------------------------------------------------------------- |
| Create Secret | `kubectl create secret generic db-secret --from-literal=password=1234` |
| Get Secret    | `kubectl get secrets`                                                  |
| Decode Secret | `kubectl get secret db-secret -o yaml`                                 |
| Delete Secret | `kubectl delete secret db-secret`                                      |

14. Node Selector
| Task         | Command                                |
| ------------ | -------------------------------------- |
| Label Node   | `kubectl label nodes worker1 env=prod` |
| View Labels  | `kubectl get nodes --show-labels`      |
| Remove Label | `kubectl label nodes worker1 env-`     |

15. Node Affinity
| Task         | Command                              |
| ------------ | ------------------------------------ |
| View Labels  | `kubectl get nodes --show-labels`    |
| Apply YAML   | `kubectl apply -f node-affinity.yml` |
| Describe Pod | `kubectl describe pod podname`       |

Types:

RequiredDuringSchedulingIgnoredDuringExecution
PreferredDuringSchedulingIgnoredDuringExecution

16. Taints & Tolerations
| Task         | Command                                            |
| ------------ | -------------------------------------------------- |
| Add Taint    | `kubectl taint node worker1 env=prod:NoSchedule`   |
| View Taints  | `kubectl describe node worker1`                    |
| Remove Taint | `kubectl taint nodes worker1 env=prod:NoSchedule-` |

17. RBAC
| Task               | Command                            |
| ------------------ | ---------------------------------- |
| Create Role        | `kubectl apply -f role.yml`        |
| Create RoleBinding | `kubectl apply -f rolebinding.yml` |
| Get Roles          | `kubectl get roles`                |
| Get RoleBindings   | `kubectl get rolebindings`         |

18. Ingress
| Task                  | Command                        |
| --------------------- | ------------------------------ |
| Install NGINX Ingress | Helm                           |
| Get Ingress           | `kubectl get ingress`          |
| Apply Ingress         | `kubectl apply -f ingress.yml` |
| Describe Ingress      | `kubectl describe ingress app` |

19. Helm Commands
| Task              | Command                                                                                                                                          |       |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ----- |
| Install Helm      | `curl [https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3](https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3) | bash` |
| Add Repo          | `helm repo add bitnami https://charts.bitnami.com/bitnami`                                                                                       |       |
| Update Repo       | `helm repo update`                                                                                                                               |       |
| Install Chart     | `helm install nginx bitnami/nginx`                                                                                                               |       |
| List Releases     | `helm list`                                                                                                                                      |       |
| Upgrade Release   | `helm upgrade nginx bitnami/nginx`                                                                                                               |       |
| Rollback Release  | `helm rollback nginx 1`                                                                                                                          |       |
| Uninstall Release | `helm uninstall nginx`                                                                                                                           |       |
20. ArgoCD Commands
| Task                 | Command                                                    |
| -------------------- | ---------------------------------------------------------- |
| Install ArgoCD       | `kubectl apply -n argocd -f install.yaml`                  |
| Get Pods             | `kubectl get pods -n argocd`                               |
| Get Initial Password | `kubectl get secret argocd-initial-admin-secret -n argocd` |
| Sync Application     | `argocd app sync myapp`                                    |
| List Applications    | `argocd app list`                                          |
21. Persistent Volumes
| Task         | Command                    |
| ------------ | -------------------------- |
| Get PV       | `kubectl get pv`           |
| Get PVC      | `kubectl get pvc`          |
| Apply PVC    | `kubectl apply -f pvc.yml` |
| Describe PVC | `kubectl describe pvc`     |
22. Monitoring (Prometheus + Grafana)

| Task                 | Command                                                                                 |
| -------------------- | --------------------------------------------------------------------------------------- |
| Add Repo             | `helm repo add prometheus-community https://prometheus-community.github.io/helm-charts` |
| Update Repo          | `helm repo update`                                                                      |
| Install Stack        | `helm install monitoring prometheus-community/kube-prometheus-stack`                    |
| Get Pods             | `kubectl get pods -n default`                                                           |
| Port Forward Grafana | `kubectl port-forward svc/monitoring-grafana 3000:80`                                   |
23. Terraform + Kubernetes
| Task       | Command                |
| ---------- | ---------------------- |
| Initialize | `terraform init`       |
| Validate   | `terraform validate`   |
| Format     | `terraform fmt`        |
| Plan       | `terraform plan`       |
| Apply      | `terraform apply`      |
| Destroy    | `terraform destroy`    |
| Show State | `terraform state list` |

24. Terraform + Helm
| Task       | Command             |
| ---------- | ------------------- |
| Initialize | `terraform init`    |
| Plan       | `terraform plan`    |
| Apply      | `terraform apply`   |
| Destroy    | `terraform destroy` |
Providers:
provider "helm" {}
provider "kubernetes" {}

25. Probe Commands

| Probe Type      | Purpose                       |
| --------------- | ----------------------------- |
| Liveness Probe  | Restart unhealthy pod         |
| Readiness Probe | Receive traffic only if ready |
| Startup Probe   | Slow starting applications    |

Verification:
kubectl describe pod podname
kubectl get events

Deployment Strategies Interview Keywords

| Strategy          | Purpose                 |
| ----------------- | ----------------------- |
| Recreate          | Stop old → Start new    |
| Rolling Update    | Gradual replacement     |
| Blue Green        | Two environments        |
| Canary            | Small % traffic testing |
| A/B Testing       | User segment testing    |
| Shadow Deployment | Mirror traffic          |





