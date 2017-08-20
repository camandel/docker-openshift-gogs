# Gogs for Red Hat OpenShift Online 3 Starter (free plan)
Gogs is the Go Git service. Learn more about it at https://gogs.io/

Running containers on OpenShift comes with certain security and other requirements. This repository contains:

* A Dockerfile for building an OpenShift-compatible Gogs image
* Various scripts used in the Docker image
* OpenShift template for deploying the image
* Usage instructions

## Notes
This repository has been created to run gogs on Red Hat OpenShift Online 3 Starter (free plan):
* It uses only one PVC mounted as /data (for repository and sqlite)
* Custom configuration (app.ini) mounted as /opt/gogs/custom/conf via ConfigMaps
* Can be accessed only in HTTPS, no SSH available

For more examples with database please look at:
https://github.com/wkulhanek/docker-openshift-gogs
https://github.com/OpenShiftDemos/gogs-openshift-docker

## Prerequisites
* An account in an OpenShift Online 3 Starter environment

## Deployment
* Sign-in into Red Hat OpenShift Online 3 Starter
* Create a new project
* Create all objects from the template via WUI or CLI:

```
oc new-app -f https://raw.githubusercontent.com/camandel/docker-openshift-gogs/master/openshift/gogs-persistent-sqlite-template.yaml
```
