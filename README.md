# Kubernetes - Minikube and Kubectl

[Install minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

[Install kubectl](https://kubernetes.io/docs/tasks/tools/)

```sh
    # create deployment
    kubectl apply -f deployment.yaml

    # check the resources created
    kubectl get deployments
    kubectl get pods

    # create service
    kubectl apply -f service.yaml

    kubectl get services

    # Check the minikube dashboard
    minikube dashboard

    # create tunnel to reach the service
    minikube service backend

    # Delete
    kubectl delete -f deployment.yaml -f service.yaml
    kubectl delete -f deployment.yaml,service.yaml
```

**Alternatively, you can use a single file**

```sh
    # create service and deployment
    kubectl apply -f deployment-single-file.yaml

    # create tunnel to reach the service
    minikube service backend

    # Delete
    kubectl delete -f deployment-single-file.yaml
```
