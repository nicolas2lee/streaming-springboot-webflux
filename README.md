# streaming-springboot-webflux
## Prerequisite
It is an example to dockerize and deploy to kubernetes in ibm cloud under the help of ibmcloud develop tool cli

### Example app
Original tech stack: 
* spring boot
* web flux
* java 8
* maven

[Runnable example](init)

### Necessary knowledge & basic knowledge about diff technos (nice to have, but not must) 
* Docker, Dockerfile
    * [Official docker doc](https://www.docker.com/)
    * [Docker course in ibm](https://cognitiveclass.ai/courses/docker-essentials)
    * [Docker best practices](https://docs.docker.com/develop/develop-images/multistage-build/)
* Kubernetes
    * [Official kubernetes doc](https://kubernetes.io/)
    * [Kubernetes course in ibm](https://cognitiveclass.ai/courses/kubernetes-course)
* Helm
    * [Official helm doc](https://helm.sh/)
    * [Helm course in ibm](https://www.ibm.com/cloud/garage/content/course/helm-fundamentals/0)
    * [Adding helm chart in kubernetes](https://cloud.ibm.com/docs/containers?topic=containers-helm)
    
## Cloudify your application
### General solution
#### Create a Dockerfile -> build -> push to docker registry
* Dockerfile
* docker build 
* docker tag
* docker push
#### Create kubernetes resource yaml or use helm to generate
* Using kubernetes yaml

    [Example using kubernetes yaml](https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/)
* Using helm

    [Example using helm to create kubernetes deployment](https://www.baeldung.com/kubernetes-helm)
#### Creating CI/CD toolchain to automatise the previous steps
### Using ibmcloud developer tools cli
[Using ibmcloud developer tools cli](complete/README.md)
# This example is part of workshop
[Main workshop](https://github.com/nicolas2lee/streaming-ibmcloud-workshop)
