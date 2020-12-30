# Getting Started with Kubernetes

Documentation based on Pluralsight course [Getting Started with Docker](https://app.pluralsight.com/library/courses/kubernetes-getting-started/)

---
## :gear: Technology

- Docker
- Kubernetes

---
## :notebook: Setup Kubernetes

### Install Kubernetes CLI

Link: https://kubernetes.io/docs/tasks/tools/install-kubectl/

#### Powershell

`Install-Script -Name 'install-kubectl' -Scope CurrentUser -Force`

 `install-kubectl.ps1 c:\kubectl`

#### Choco

`choco install Kubernetes-cli`

---

### Check Kubectl version

`kubectl version --short`

---

- Install [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Enable Kubernetes

![](images/image1.png)

---
## :construction_worker: Working with Pods

### Deploying single container pod

| Command                | Description                                       |
|:-----------------------|:--------------------------------------------------|
| `kubectl cluster-info` | Get information about running Kubernetes clusters |

![](images/image2.png)

> Clone files from [getting-started-k8s](https://github.com/nigelpoulton/getting-started-k8s) to follow steps below

- Navigate into the `Pods` folder

| Command                    | Description                    |
|:---------------------------|:-------------------------------|
| `kubectl apply -f pod.yml` | Create resource from `pod.yml` |
| `kubectl get pods --watch` | View pod status                |

![](images/image3.png)

`kubectl get pods - o wide`
- status with extra columns

![](images/image4.png)

`kubectl describe pods hello-pod`

![](images/image5.png)

### Deploying multi-container pod

`kubectl apply -f multi-pod.yml`

`kubectl get pods --watch`
- status of pods

`kubectl delete pod nginx`
or
`kubectl delete -f multi-pod.yml`

> nginx is name of pod, or you can use yml file used

## Kubernetes Services

`kubectl expose pod hello-pod --name=hello-svc --target-port=8080 --type=NodePort`

- expose pod with NodePort service

`kubectl get svc`
- view services

![](images/image6.png)

> If you're using Docker Desktop, you can view the app. with http://localhost: + the node port - based on the example above, it would be http://localhost:30859/


