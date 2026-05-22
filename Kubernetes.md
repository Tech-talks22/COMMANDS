🔹 1️⃣ Cluster & Node Commands

| Command                             | Explanation                                                  |
| ----------------------------------- | ------------------------------------------------------------ |
| `kubectl cluster-info`              | Displays Kubernetes control plane and core service endpoints |
| `kubectl get nodes`                 | Lists all nodes in the cluster                               |
| `kubectl describe node <node-name>` | Shows detailed node information                              |
| `kubectl top nodes`                 | Displays CPU and memory usage of nodes                       |


🔹 2️⃣ Pod Commands

| Command                                    | Explanation                                    |
| ------------------------------------------ | ---------------------------------------------- |
| `kubectl get pods`                         | Lists all pods in current namespace            |
| `kubectl get pods -o wide`                 | Shows pods with node, IP and extra details     |
| `kubectl describe pod <pod-name>`          | Displays detailed pod configuration and events |
| `kubectl logs <pod-name>`                  | Shows logs of a pod                            |
| `kubectl logs -f <pod-name>`               | Streams live pod logs                          |
| `kubectl exec -it <pod-name> -- /bin/bash` | Opens shell inside a running pod               |
| `kubectl delete pod <pod-name>`            | Deletes a specific pod                         |


🔹 3️⃣ Deployment Commands

| Command                                                  | Explanation                              |
| -------------------------------------------------------- | ---------------------------------------- |
| `kubectl get deployments`                                | Lists all deployments                    |
| `kubectl apply -f deployment.yaml`                       | Creates or updates deployment using YAML |
| `kubectl describe deployment <name>`                     | Shows deployment details                 |
| `kubectl scale deployment <name> --replicas=5`           | Scales deployment to 5 replicas          |
| `kubectl set image deployment/<name> container=image:v2` | Updates container image                  |
| `kubectl rollout status deployment <name>`               | Checks rollout progress                  |
| `kubectl rollout undo deployment <name>`                 | Rolls back to previous version           |
| `kubectl rollout history deployment <name>`              | Shows deployment revision history        |


🔹 4️⃣ ReplicaSet / StatefulSet / DaemonSet

| Command                                         | Explanation        |
| ----------------------------------------------- | ------------------ |
| `kubectl get rs`                                | Lists ReplicaSets  |
| `kubectl get statefulsets`                      | Lists StatefulSets |
| `kubectl get daemonsets`                        | Lists DaemonSets   |
| `kubectl scale statefulset <name> --replicas=3` | Scales StatefulSet |
| `kubectl delete daemonset <name>`               | Deletes DaemonSet  |


🔹 5️⃣ Job & CronJob

| Command                           | Explanation              |
| --------------------------------- | ------------------------ |
| `kubectl get jobs`                | Lists batch jobs         |
| `kubectl get cronjobs`            | Lists scheduled CronJobs |
| `kubectl delete job <name>`       | Deletes a job            |
| `kubectl describe cronjob <name>` | Shows CronJob details    |

🔹 6️⃣ Service Commands

| Command                                                      | Explanation                   |
| ------------------------------------------------------------ | ----------------------------- |
| `kubectl get services`                                       | Lists services                |
| `kubectl describe service <name>`                            | Shows service configuration   |
| `kubectl expose deployment <name> --type=NodePort --port=80` | Exposes deployment as service |
| `kubectl delete service <name>`                              | Deletes a service             |

🔹 7️⃣ Ingress Commands

| Command                           | Explanation              |
| --------------------------------- | ------------------------ |
| `kubectl get ingress`             | Lists ingress resources  |
| `kubectl describe ingress <name>` | Shows routing rules      |
| `kubectl delete ingress <name>`   | Deletes ingress resource |


🔹 8️⃣ ConfigMap & Secret Commands

| Command                                                                 | Explanation                       |
| ----------------------------------------------------------------------- | --------------------------------- |
| `kubectl get configmaps`                                                | Lists ConfigMaps                  |
| `kubectl create configmap my-config --from-file=file.txt`               | Creates ConfigMap from file       |
| `kubectl get secrets`                                                   | Lists secrets                     |
| `kubectl create secret generic my-secret --from-literal=password=admin` | Creates secret from literal value |

🔹 9️⃣ Storage (PV & PVC)

| Command                       | Explanation                  |
| ----------------------------- | ---------------------------- |
| `kubectl get pv`              | Lists PersistentVolumes      |
| `kubectl get pvc`             | Lists PersistentVolumeClaims |
| `kubectl describe pvc <name>` | Shows PVC binding status     |
| `kubectl delete pvc <name>`   | Deletes PVC                  |


🔹 🔟 Namespace Commands

| Command                        | Explanation           |
| ------------------------------ | --------------------- |
| `kubectl get namespaces`       | Lists namespaces      |
| `kubectl create namespace dev` | Creates new namespace |
| `kubectl delete namespace dev` | Deletes namespace     |



🔹 1️⃣1️⃣ Scheduling & Labels

| Command                                                 | Explanation                   |
| ------------------------------------------------------- | ----------------------------- |
| `kubectl label pod <pod-name> env=prod`                 | Adds label to pod             |
| `kubectl get pods --show-labels`                        | Displays labels               |
| `kubectl taint nodes <node-name> key=value:NoSchedule`  | Prevents pods from scheduling |
| `kubectl taint nodes <node-name> key=value:NoSchedule-` | Removes taint                 |



🔹 1️⃣2️⃣ Autoscaling

| Command                                                                | Explanation                       |
| ---------------------------------------------------------------------- | --------------------------------- |
| `kubectl autoscale deployment <name> --cpu-percent=50 --min=1 --max=5` | Creates Horizontal Pod Autoscaler |
| `kubectl get hpa`                                                      | Lists autoscalers                 |



🔹 1️⃣3️⃣ Resource Monitoring

| Command              | Explanation                              |
| -------------------- | ---------------------------------------- |
| `kubectl top pods`   | Shows pod CPU & memory usage             |
| `kubectl top nodes`  | Shows node resource usage                |
| `kubectl get events` | Shows cluster events for troubleshooting |


🔹 1️⃣4️⃣ RBAC Commands


| Command                           | Explanation                 |
| --------------------------------- | --------------------------- |
| `kubectl get roles`               | Lists namespace roles       |
| `kubectl get clusterroles`        | Lists cluster-wide roles    |
| `kubectl get rolebindings`        | Lists role bindings         |
| `kubectl get clusterrolebindings` | Lists cluster role bindings |


🔹 1️⃣5️⃣ Debugging & General

| Command                                       | Explanation                              |
| --------------------------------------------- | ---------------------------------------- |
| `kubectl get all`                             | Lists all resources in namespace         |
| `kubectl logs <pod> --previous`               | Shows logs of previous crashed container |
| `kubectl apply -f file.yaml --dry-run=client` | Validates YAML without applying          |
| `kubectl rollout restart deployment <name>`   | Restarts deployment with zero downtime   |








                                                                           Advanced Kubernetes Troubleshooting Commands


🔥 1️⃣ Pod Troubleshooting

| Command                                    | Explanation                         | When to Use                       |
| ------------------------------------------ | ----------------------------------- | --------------------------------- |
| `kubectl get pods -o wide`                 | Shows pod IP, node, status          | When pod is not reachable         |
| `kubectl describe pod <pod-name>`          | Shows events, errors, restart count | Pod is Pending / CrashLoopBackOff |
| `kubectl logs <pod-name>`                  | Shows container logs                | Application errors                |
| `kubectl logs <pod-name> --previous`       | Shows logs of crashed container     | CrashLoopBackOff issue            |
| `kubectl exec -it <pod-name> -- /bin/bash` | Access inside container             | Debug runtime issues              |
| `kubectl get pod <pod-name> -o yaml`       | Shows full pod definition           | Config mismatch debugging         |


🔥 2️⃣ CrashLoopBackOff Debugging


| Command                                                    | Explanation                 | Why                       |
| ---------------------------------------------------------- | --------------------------- | ------------------------- |
| `kubectl describe pod <pod>`                               | Shows restart reason        | Identify crash cause      |
| `kubectl logs <pod> --previous`                            | Shows last crashed logs     | Root cause analysis       |
| `kubectl get events --sort-by=.metadata.creationTimestamp` | Shows recent cluster events | Check scheduling failures |
| `kubectl top pod <pod>`                                    | Shows CPU/memory usage      | Detect OOMKilled issue    |



🔥 3️⃣ Pending Pod Troubleshooting

| Command                        | Explanation                 | Why                          |
| ------------------------------ | --------------------------- | ---------------------------- |
| `kubectl describe pod <pod>`   | Shows scheduling errors     | Check insufficient resources |
| `kubectl get nodes`            | Lists available nodes       | Check node availability      |
| `kubectl describe node <node>` | Shows allocatable resources | Resource shortage issue      |
| `kubectl get pvc`              | Check PVC binding           | Storage-related pending      |


🔥 4️⃣ Node Troubleshooting

| Command                                    | Explanation             | Why                             |
| ------------------------------------------ | ----------------------- | ------------------------------- |
| `kubectl get nodes`                        | Shows node status       | Node Ready/NotReady check       |
| `kubectl describe node <node>`             | Detailed node info      | Disk pressure / memory pressure |
| `kubectl top node <node>`                  | Resource usage          | CPU/Memory bottleneck           |
| `kubectl cordon <node>`                    | Mark node unschedulable | Prevent new pods scheduling     |
| `kubectl drain <node> --ignore-daemonsets` | Safely evicts pods      | Node maintenance                |
| `kubectl uncordon <node>`                  | Makes node schedulable  | Bring node back                 |



🔥 5️⃣ Service Troubleshooting

| Command                           | Explanation           | Why                         |
| --------------------------------- | --------------------- | --------------------------- |
| `kubectl get svc`                 | Lists services        | Verify service existence    |
| `kubectl describe svc <svc-name>` | Shows endpoints       | Check target pod mapping    |
| `kubectl get endpoints`           | Shows backend pod IPs | Service not routing traffic |
| `kubectl get pods --show-labels`  | Shows pod labels      | Label mismatch issue        |


🔥 6️⃣ Ingress Troubleshooting

| Command                                   | Explanation                    | Why                       |
| ----------------------------------------- | ------------------------------ | ------------------------- |
| `kubectl get ingress`                     | Lists ingress resources        | Verify ingress exists     |
| `kubectl describe ingress <name>`         | Shows routing rules            | Check backend mapping     |
| `kubectl get pods -n <ingress-namespace>` | Checks ingress controller pods | Controller down issue     |
| `kubectl logs <ingress-pod>`              | Shows ingress errors           | Routing failure debugging |


🔥 7️⃣ Deployment Troubleshooting

| Command                                     | Explanation            | Why                |
| ------------------------------------------- | ---------------------- | ------------------ |
| `kubectl get deployments`                   | Lists deployments      | Check availability |
| `kubectl describe deployment <name>`        | Shows replica status   | Replica mismatch   |
| `kubectl rollout status deployment <name>`  | Shows rollout progress | Stuck rollout      |
| `kubectl rollout history deployment <name>` | Shows revisions        | Version tracking   |
| `kubectl rollout undo deployment <name>`    | Rollback deployment    | Failed release fix |


🔥 8️⃣ Storage Troubleshooting (PV/PVC)

| Command                       | Explanation           | Why                       |
| ----------------------------- | --------------------- | ------------------------- |
| `kubectl get pvc`             | Shows claim status    | Pending PVC issue         |
| `kubectl describe pvc <name>` | Shows binding details | StorageClass problem      |
| `kubectl get pv`              | Lists volumes         | Check volume availability |
| `kubectl describe pv <name>`  | Shows volume details  | Access mode mismatch      |


🔥 9️⃣ Network Troubleshooting


| Command                                             | Explanation       | Why                        |
| --------------------------------------------------- | ----------------- | -------------------------- |
| `kubectl exec -it <pod> -- ping <service-name>`     | Tests service DNS | DNS issue                  |
| `kubectl exec -it <pod> -- nslookup <service-name>` | Tests cluster DNS | CoreDNS issue              |
| `kubectl get pods -n kube-system`                   | Lists system pods | Check CNI or DNS failure   |
| `kubectl logs -n kube-system <coredns-pod>`         | Shows DNS logs    | Service resolution problem |


🔥 🔟 Resource & Performance Debugging

| Command                          | Explanation            | Why                 |
| -------------------------------- | ---------------------- | ------------------- |
| `kubectl top pods`               | Shows pod usage        | High CPU issue      |
| `kubectl top nodes`              | Shows node usage       | Node overload       |
| `kubectl describe pod <pod>`     | Shows resource limits  | OOMKilled reason    |
| `kubectl edit deployment <name>` | Modify resource limits | Increase memory/CPU |


🔥 1️⃣1️⃣ RBAC Troubleshooting

| Command                                     | Explanation            | Why                 |
| ------------------------------------------- | ---------------------- | ------------------- |
| `kubectl get roles`                         | Lists namespace roles  | Check permission    |
| `kubectl get rolebindings`                  | Lists role bindings    | Verify user binding |
| `kubectl auth can-i create pods --as=user1` | Checks user permission | RBAC denial issue   |


🔥 1️⃣2️⃣ Cluster-Level Debugging

| Command                               | Explanation                   | Why                    |
| ------------------------------------- | ----------------------------- | ---------------------- |
| `kubectl get componentstatuses`       | Shows control plane health    | API server issue       |
| `kubectl get events --all-namespaces` | Shows cluster-wide events     | Global issue check     |
| `kubectl api-resources`               | Lists all resource types      | CRD validation         |
| `kubectl version`                     | Shows client & server version | Version mismatch issue |



🎯 Most Common Interview Scenarios

| Problem              | First Command to Run       |
| -------------------- | -------------------------- |
| Pod CrashLoopBackOff | `kubectl describe pod`     |
| Pod Pending          | `kubectl describe pod`     |
| Service not working  | `kubectl describe svc`     |
| Ingress not routing  | `kubectl describe ingress` |
| Node NotReady        | `kubectl describe node`    |
| High CPU usage       | `kubectl top pods`         |
| Deployment failed    | `kubectl rollout status`   |













