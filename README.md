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

8. Create value.yaml

9. Helm Install
`helm repo add bitnami https://charts.bitnami.com/bitnami`

`helm install jenkins --set jenkinsPassword=bct1234 bitnami/jenkins -n jenkins -f value.yaml`

10. Verifications

`kubectl get pod -n jenkins`

`kubectl get svc -n jenkins`

`kubectl get pvc -n jenkins`

`kubectl get serviceaccount -n jenkins`

`kubectl get role -n jenkins`

`kubectl get rolebinding -n jenkins`

11. Create httpproxy.yaml

12. Create HTTPProxy

`kubectl apply -f httpproxy.yaml -n jenkins`

`kubectl get httpproxy -n jenkins`

`kubectl describe httpproxy jenkins-web -n jenkins`
