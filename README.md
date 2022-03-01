# Jenkins-Helm

1. Create working directory

`mkdir -p devops-tools-install/jenkins-np`

`cd devops-tools-install/jenkins-np`

2. Create Namespace

`kubectl create ns jenkins`

3. Create Service Account

`kubectl create serviceaccount jenkins -n jenkins`

4. Create role.yaml

5. Create Role
`kubectl apply -f role.yaml -n jenkins`

6. Create rolebinding.yaml

7. Create Role Binding

`kubectl apply -f rolebinding.yaml -n jenkins`

8. Create ConfigMap

`kubectl -n jenkins create configmap ad-cert --from-file=bctad01.cer`

`kubectl -n jenkins create configmap gitlab-cert --from-file=gitlab.cer`

9. Create value.yaml

10. Helm Install

`helm repo add bitnami https://charts.bitnami.com/bitnami`

`helm install jenkins --set jenkinsPassword=bct1234 bitnami/jenkins -n jenkins -f value.yaml`

11. Verifications

`kubectl get pod -n jenkins`

`kubectl get svc -n jenkins`

`kubectl get pvc -n jenkins`

`kubectl get serviceaccount -n jenkins`

`kubectl get role -n jenkins`

`kubectl get rolebinding -n jenkins`

12. Create httpproxy.yaml

13. Create HTTPProxy

`kubectl apply -f httpproxy.yaml -n jenkins`

`kubectl get httpproxy -n jenkins`

`kubectl describe httpproxy jenkins-web -n jenkins`

# Global Settings
1. Install RBAC Plugin

2. Enable LDAP

3. Create Global Role

4. Assign Global Role
