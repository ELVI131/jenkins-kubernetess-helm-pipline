# jenkins-kubernetess-helm-pipline
Install Helm
Install jenkins using helm

helm repo add jenkins https://charts.jenkins.io
helm repo update


helm upgrade --install myjenkins jenkins/jenkins

Run the command to get the admin password

 kubectl exec --namespace default -it svc/myjenkins -c jenkins -- /bin/cat /run/secrets/chart-admin-password && echo


Run the command to establishes a tunnel

kubectl --namespace default port-forward svc/myjenkins 8080:8080

open jenkins in web using  http://localhost:8080 

Install  additional plugins 

Create new pipeline 

Run build 

Check the console output to see the resulte
