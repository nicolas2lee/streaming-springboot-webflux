## Get initial app
Get initial app from init 

## Auto generation of configuration
Since it's an existing application, execute below command
    
    ibmcloud dev enable
For new project, using

    ibmcloud dev create
## Without customization

### build your app
    ibmcloud dev build (--debug for debug mode)
### deploy your app
    ibmcloud deploy --target container
or add below block into cli-config.yml
 
    deploy-target: "container"
    deploy-image-target: "us.icr.io/streaming/streamingspringbootwebflux"
    ibm-cluster: "streaming"
If you have this issue:

    Executing kubectl get clusterrolebinding tiller -n kube-system
    
    
    FAILED
    Executing kubectl create clusterrolebinding tiller --clusterrole=cluster-admin 
    Failed to execute the action:  exit status 1: Error from server (NotFound): 
    --serviceaccount=kube-system:default -n kube-system
    
    clusterrolebindings.rbac.authorization.k8s.io "tiller" not found
    
    
    FAILED
    The 'kubectl get clusterrolebinding tiller -n kube-system' command failed to 
    complete due to: exit status 1
    
    clusterrolebinding.rbac.authorization.k8s.io "tiller" created
That's because it needs helm to install the helm chart into kubernetes, and you should install tiller into your kubernetes cluster

    kubectl create serviceaccount tiller -n kube-system
    
    kubectl create clusterrolebinding tiller --clusterrole=cluster-admin --serviceaccount=kube-system:tiller -n kube-system

[For more details](https://cloud.ibm.com/docs/containers?topic=containers-helm)

## Customize your own dockerfile or helm chart
The auto generated config is good, but now always adapt to our business needs, so sometimes or even at most time we need define our custom dockerfile & helm chart
    