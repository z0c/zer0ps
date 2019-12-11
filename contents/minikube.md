# Minikube

Minikube is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a VM on your laptop for users looking to try out Kubernetes or develop with it day-to-day.

## Installation

### macOS

```
$ brew cask install minikube
```

## Usage

Starting up minikube

```
$ minikube start
```

Checking if the service is running

```
$ minikube status
```

Finding out running IP

```
$ minikube ip
```

### Pushing images to minikube
```
$ eval $(minikube docker-env)
$ docker build --rm -f Dockerfile -t image_name:latest .
```

### Starting with a specific version

  `minikube start --kubernetes-version=v1.15.0`

