# Guestbook Example for OpenShift / Minishift

The guestbook example shows how to build a simple multi-tier web application using Kubernetes and Docker. The application consists of a web front end, Redis master for storage, and replicated set of Redis slaves, all for which we will create Kubernetes deployments, pods, and services.

There are two versions of this application. Version 1 (in the `v1` directory) is the example application itself, while version 2 (in the `v2` directory) extends the application by adding additional features that leverage the Watson Tone Analyzer service. The `v1` directory has a `README.md` file if you are interested in exploring the base example on your own with a Kubernetes cluster.

The `v2` directory contains the application version that will be the focus for the rest of this hands-on guide. In this guide, you will see how to install and configure a local copy of [Minishift](https://www.okd.io/minishift/), an open source version of the OpenShift container platform that is optimized for smaller size and development use cases.

You will add to this cluster support for the [Operator Framework](https://github.com/operator-framework/) and the [IBM Cloud operator](https://github.com/IBM/cloud-operators). Using the IBM Cloud operator, you will be able to create an instance of the Watson Tone Analyzer service and configure a Kubernetes secret in the cluster.

With the credentials for the Tone Analyzer service added to the cluster, you will then be able to create the enhanced guestbook application on your Minishift cluster. This application can also be deployed to an existing OpenShift 3.9 or higher cluster by skipping the Minishift cluster setup steps. The application, including IBM Cloud operator may also be deployed on an OpenShift 4.x cluster by skipping the Minishift cluster setup and the OLM / operator marketplace setup steps (support for operator marketplace ships in OpenShift 4.x).

## Prerequisites

* Workstation (MacOS, Linux or Windows 10) with hypervisor support, either native to the OS or through VirtualBox.
* An [IBM Cloud account](https://ibm.biz/BdzACM) - only a Standard/Lite account is needed.
* For Windows 10, support for a bash shell, for example either by setting up [git bash](https://gitforwindows.org/) or the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
* The [IBM Cloud CLI](https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli) installed on your workstation.
* Internet connectivity for downloading Minishift and connecting to the IBM Cloud.
* Optional - for building the container images for the guestbook application: [Docker Desktop for Mac and Windows](https://www.docker.com/products/docker-desktop) or Docker for your Linux system, and the `make` utility.

## Time required

Expect to spend about 45 minutes to create the cluster, deploy the operator framework and IBM Cloud operator and then configure the guestbook application on the cluster. Additional time may be needed for configuring your workstation hypervisor configuration.

## Getting started

Begin by creating a local clone of this repository on your workstation with either git clone:

```text
git clone https://github.com/timroster/guestbook-openshift.git
```

Or by downloading a zip file of the repository and unpacking locally.

## Steps to install Minishift, configure Operator Framework support, create the IBM Cloud operator and deploy the guestbook application

* [Set up Minishift on your system](workshop/minishift.md)
* [Install Operator Framework and IBM Cloud Operator](workshop/ibm-operator.md)
* [Create an instance of the Watson Tone Analyzer service on IBM Cloud](workshop/create-tone.md)
* [Deploy the enhanced guestbook application](workshop/deploy-guestbook.md)

## Summary and next steps

Visit the IBM Developer [OpenShift on IBM Cloud collection](https://developer.ibm.com/collections/openshift-on-ibm/) to learn more about using OpenShift on IBM Cloud. For additional step-by-step learning activities related to OpenShift check out [learn.openshift.com](https://learn.openshift.com)
