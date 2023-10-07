# Kubernetes Playground

# Overview
This repo will be used to learn kubernetes hands on using kind containers to apply kubernetes deployments

# Topic List
- [Deployments](notes/deployments.md)
- [Services](notes/services.md)
- [Ingress](notes/ingress.md`


# Steps
- Create docker image
- create local registery
- create kind cluster
- connect local registry to kind cluster
- push app image to local registry
- deploy using kubernetes

# Create docker image
`docker build -t dockerized-react-app ./dockerized-react-app/`

## Create local registry
`docker run -d -p 5000:5000 --name local-registry --restart=always registry:2;`

## Create kind cluster 
- create kind config
`kind create cluster --image=kindest/node:v1.21.12 --name k8s-playground --config ./kind_config.yaml`

- connect docker registry to kind network
`docker network connect kind local-registry`

- connect registry to kind 
`kubectl apply -f ./kind_configmap.yaml`




