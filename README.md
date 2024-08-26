K8s cluster consists of Master Node and Worker Nodes. [Master Node can be  more than 1]

**Components present in Master Node** : 
 1. Kube API server
 2. ETCD
 3. Scheduler
 4. Controller-manager (Node Controller, Replication Controller etc..)

**Kube API Server** : 
Whatever we do in k8s whether we create a pod it is one API call & We need to make API calls to do anything in K8's & through Kubectl we can intereact with k8s API.
Whatever we passess through CLI, It goes to API server & API server first validates the request & passes the request.
To connect kubectl with API, kubectl should know we API server is ...& for that we install Kubectl and configure config file. (Config file is nothing but wr it contains the cluster info)
Thrugh this config file, Kubectl will interact with api server.

      **flow** : When user passes a req thorugh kubectl, first kubectl passes the req to API server & then API server will Authentciate and Authorize the request before proceeding it & it will validate 
        and process the request, and these destails will be presisted in **ETCD**




   


