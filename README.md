# Deploying multiple images to a Kubernetes cluster with your Shippable pipeline.

![AyeAye](https://github.com/devops-recipes/deploy-kubernetes-basic/raw/master/public/resources/images/captain.png)

This repository demonstrates the following :
- Setup CI for a NodeJS application that builds a docker image and deploys it to DockerHub.
- Setup a CD pipeline to deploy the NodeJS docker image and an nginx image to a Kubernetes cluster using many strategies documented [here]().

## Prerequisites to run this sample

* Source control account (e.g. GitHub, Bitbucket, Gitlab)
* Shippable account (sign up for free at www.shippable.com)
* Kubernetes cluster.

## Setup
* Fork this repo into your local repository in your source control account.
* Login into Shippable with your source control account(wwww.shippable.com).
* Create a [Docker Hub integration](http://docs.shippable.com/platform/integration/dockerRegistryLogin/) on shippable to your docker hub.
* All your CI configuration is in `shippable.yml` file, while you will modify next to reflect your integration.
* Update the integrationName in the integration.hub section with the integration name created above.
* Change the DOCKER_REPO and DOCKER_ACC to point to your repo and docker account.
* Next, follow these [CI Setup Instructions](http://docs.shippable.com/ci/runFirstBuild/) to enable your forked project for CI.
* Build your CI project by clicking on the build button. Once the build completes, the NodeJS docker image will be pushed to your DockerHub account.
* Create the Kubernetes integration using instructions provided [here]().

## Add the pipeline  in Shippable
* Sign in with your shippable account, select your subscription from the dropdown menu in upper left (three horizontal lines).
* Select the Pipelines tab.
* Select the "+" icon in the upper right.
* Select the source control repo where your fork is. This will render all the jobs in the Single pane of glass (SPOG).
* Run the pipeline following instructions [here]().

## CI Console Output
![CI Console Output](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/console.jpg)

##Build link
[CI build on Shippable](https://app.shippable.com/github/devops-recipes/deploy-kubernetes-multi-container/runs/7/1/console)

##Build status badge
[![Run Status](https://api.shippable.com/projects/58f98b298c0a6707003b237a/badge?branch=master)](https://app.shippable.com/github/devops-recipes/deploy-kubernetes-multi-container)


## Pipeline View
![Pipeline1](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy1-pipeline-view.png)
![Pipeline2](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy2-pipeline-view.png)
![Pipeline3](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy3a3b-pipeline-view.png)

## Deploy job View
![Deploy1](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy1-job-view.png)
![Deploy2](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy2-job-view.png)
![Deploy3](https://github.com/devops-recipes/deploy-kubernetes-multi-container/raw/master/public/resources/images/deploy3b-job-view.png)
