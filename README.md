# belajar

This repo is about my journey of learning kubernetes

## Tools installed

1. Docker version 26.1.5+dfsg1, build a72d7cd : used as the nodes/resources of the kubernetes
2. Kind version 0.30.0 : used as the kubernetes distribution
3. Flux version 2.7.5 : used as the runner to run the changes

## Installation

### Docker

```
sudo apt install docker.io -y
```

### Kind

```
brew install Kind
```

### Flux

```
curl -s https://fluxcd.io/install.sh | sudo bash
```

## Steps to setup the cluster

```
kind create cluster --name belajar
```

It is creating a kind kubernetes cluster named kind-belajar
