# Kubernetes - Minikube and Kubectl

[Install minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

[Install kubectl](https://kubernetes.io/docs/tasks/tools/)


## Example using Kubernetes commands

```sh
    # Build the image
    docker build -t kub-first-app .

    # Change the image name
    docker tag kub-first-app falamarcaodocker/kub-first-app

    # Login to Docker Hub
    docker login

    # Push the image
    docker push falamarcaodocker/kub-first-app
```

```sh
    kubectl create deployment first-app --image=falamarcaodocker/kub-first-app

    kubctl expose deployment first-app --type=LoadBalancer  --port=8080

    kubectl get deployments
    kubectl get pods
    kubectl get services

    kubectl scale deployment/first-app --replicas=3

    kubectl set image deploymeny/first-app kub-first-app=falamarcaodocker/kub-first-app:2

```

## Example using configuration YAML files

```sh
    # Build the image
    docker build -t kub-first-app .

    # Change the image name
    docker tag kub-first-app falamarcaodocker/kub-first-app

    # Login to Docker Hub
    docker login

    # Push the image
    docker push falamarcaodocker/kub-first-app
```

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

    # Or delete by label
    kubectl delete deployments,services -l group=example

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
