# Jenkins-Helm

Create working directory

`mkdir -p devops-tools-install/jenkins-np`

`cd devops-tools-install/jenkins-np`

Create Namespace

`kubectl create ns jenkins`

Create Service Account

`kubectl create serviceaccount jenkins -n jenkins`

Create role.yaml

Create Role
`kubectl apply -f role.yaml -n jenkins`

Create rolebinding.yaml

Create Role Binding

`kubectl apply -f rolebinding.yaml -n jenkins`

Create value.yaml

Helm Install
`helm repo add bitnami https://charts.bitnami.com/bitnami`

`helm install jenkins --set jenkinsPassword=bct1234 bitnami/jenkins -n jenkins -f value.yaml`
