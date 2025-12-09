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

First step is creating a kind kubernetes cluster named kind-belajar or something. Meanwhile, prepare the repository which is on github in this case. The repository can be either public or private but it need to have an access token that will be used by flux to pull the code and run it in our local cluster
