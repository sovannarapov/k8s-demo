### Repository for the K8s

#### K8s manifest files

- mongo-config.yaml
- mongo-secret.yaml
- mongo.yaml
- webapp.yaml

#### K8s commands

##### start Minikube

    minikube start --driver docker

##### check status

    minikube status

### apply commands in order

    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-config.yaml
    kubectl apply -f webapp.yaml

##### get minikube node's ip address

    minikube ip

##### get basic info about k8s components

    kubectl get node
    kubectl get node -o wide
    kubectl get pod
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get secret
    kubectl get svc
    kubectl get all

##### get detailed info about a specific component

    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs

    kubectl logs {pod-name}

##### stop your Minikube cluster

    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible**

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:

    minikube service webapp-service
