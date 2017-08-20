# Gogs for OpenShift Online 3 Starter (free plan)
Gogs is the Go Git service. Learn more about it at https://gogs.io/

Running containers on OpenShift comes with certain security and other requirements. This repository contains:

* A Dockerfile for building an OpenShift-compatible Gogs image
* Various scripts used in the Docker image
* OpenShift templates for deploying the image
* Usage instructions

## Prerequisites
* An account in an OpenShift Online 3 Starter environment and a project (it uses sqlite as Starter plan has only one Physical Volume)

## Deployment
Gogs can be easily deployed using the included template in `openshift` folder:

```
oc new-app -f https://raw.githubusercontent.com/camandel/docker-openshift-gogs/master/openshift/gogs-persistent-sqlite-template.yaml
```
