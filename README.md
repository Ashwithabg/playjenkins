# k8s-jenkins

helm repo add jenkinsci https://charts.jenkins.io/

helm list

helm search repo jenkins

kubectl create namespace jenkins

helm show values jenkinsci/jenkins > jenkins-values.yaml

helm install jenkins jenkinsci/jenkins --version 2.6.4 --values jenkins-updated-values.yaml --namespace jenkins

helm install jenkins jenkinsci/jenkins --version 2.6.4 --values updated-values.yaml --namespace jenkins

printf $(kubectl get secret --namespace jenkins jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo


### 7. Fork this repository into your own GitHub account:
s
https://github.com/saptaktakalkar/playjenkins

Update the forked repo (make sure you commit these changes):
* Update registry environment variable in Jenkinsfile with your own dockerhub repository which you had created in step 7 above.
* Update the imagename in myweb.yaml with your own dockerhub repository name.
* Update the git repository url in Checkout SCM stage in Jenkinsfile with your own repository url where you have forked the above playjenkins repository.


### 8. Setup New Item

kubectl get pods --namespace jenkins -w

Blue Ocean Pipleline -- for GitHub


### 9. Docker error

9.1 Login to all worker nodes and execute this command:

chmod 666 /var/run/docker.sock

9.2 Authentication
Add following two credentials in Jenkins:
  Kind: Username with password
  ID: dockerhub

### 10. Kubernetes deployment error
Add following two credentials in Jenkins:
  Kind: Kubernetes configuration (kubeconfig)
  ID: mykubeconfig