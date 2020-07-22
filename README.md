# read.me

## insall ANSIBLE
    $ sudo apt-get update
    $ sudo apt-get install software-properties-common
    $ sudo apt-add-repository --yes --update ppa:ansible/ansible
    $ sudo apt-get install ansible

## Install TERRAFORM

## install minikube

## Docker params
	$ eval $(minikube docker-env)
	$ sudo systemctl restart docker

# Manual installation of 
## install helm 
	$ curl https://helm.baltorepo.com/organization/signing.asc | sudo apt-key add -
	$ sudo apt-get install apt-transport-https --yes
	$ echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
	$ sudo apt-get update
	$ sudo apt-get install helm

## create new Namespace "development"
	$ kubectl create namespace development

## install gogs
	$ helm install gogs ./gogs -n development

## after gogs installed need create new User and Repo
	$ kubectl port-forward svc/gogs-gogs 8080:80 -n development
	And browse 127.0.0.1:8080. Create User and repo (I did names "test" for all)
	# optional for secure connetction to your Repo
	Add your ssh public-key http://127.0.0.1:8080/user/settings/ssh to created Repo for allow ssh pull (
	# add project "test" in repo
	$ git clone http://127.0.0.1:8080/test/test.git
    $ git add --all
	$ git commit -m "added project test"
	$ git push



	

