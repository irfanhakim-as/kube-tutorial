# Kubernetes Tutorial

## Table of Contents

- [Kubernetes Tutorial](#kubernetes-tutorial)
  - [Table of Contents](#table-of-contents)
  - [Create a namespace](#create-a-namespace)
  - [Deploying manifests](#deploying-manifests)
  - [Update resource](#update-resource)
    - [Solution 1: Redeploy manifest](#solution-1-redeploy-manifest)
    - [Solution 2: Edit resource directly](#solution-2-edit-resource-directly)
  - [Delete resource](#delete-resource)
    - [Solution 1: Delete using manifest](#solution-1-delete-using-manifest)
    - [Solution 2: Delete resource directly](#solution-2-delete-resource-directly)

## Create a namespace

Create a namespace for our tutorial

```sh
kubectl create ns tutorial
```

## Deploying manifests

Deploy configmap, secret and deployment to namespace `tutorial`

```sh
kubectl apply -f ./manifests/cm.yaml -f ./manifests/secret.yaml -f ./manifests/deploy.yaml -n tutorial
```

## Update resource

### Solution 1: Redeploy manifest

For example, make changes to the deployment manifest

```sh
nano ./manifests/deploy.yaml
```

Redeploy the deployment manifest

```sh
kubectl apply -f ./manifests/deploy.yaml -n tutorial
```

### Solution 2: Edit resource directly

For example, update the deployment, `hello-world`, directly

```sh
kubectl edit deployment hello-world -n tutorial
```

## Delete resource

### Solution 1: Delete using manifest

For example, delete the configmap using its manifest

```sh
kubectl delete -f ./manifests/cm.yaml -n tutorial
```

### Solution 2: Delete resource directly

Delete the configmap, `hello-world-cm`, directly

```sh
kubectl delete configmap hello-world-cm -n tutorial
```
