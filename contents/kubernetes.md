# Kubernetes

### Creating a service

```
$ kubectl create namespace ${namespace_name}
$ kubectl create -f ${kubernetes_config}.yaml
$ kubectl get pods --namespace ${namespace_name}
```

### Apply

Apply is a command that will sync the state of the cluster to with local files

```
$ kubectl apply -f <file name>
```

### Services

Showing state and port mappings of a service

```
$ kubectl get service --namespace jenkins
```

Deleting a StatefulSet

```
$ kubectl delete sts ${image_name} --namespace=${namespace_name}
```

SSHing to a container

```
$ kubectl --namespace=${namespace_name} exec -it ${instance_name} -- /bin/bash
```

## Config

Listing contexts

```
$ kubectl config get-contexts
CURRENT   NAME              CLUSTER                                                      AUTHINFO                                                     NAMESPACE
*         cluster-name arn:aws:eks:us-west-2:999999999:cluster/cluster-name arn:aws:eks:us-west-2:999999999:cluster/cluster-name
          minikube          minikube                                                     minikube
``

## Debugging an image

    kubectl run -i -t tools --image=arrowsama/netshoot --restart=Never --rm=true
