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

      **flow** : When user passes a req thorugh kubectl, first kubectl sends the req to API server & before proceeding, the API server 
                 will Authentciate and Authorize the request & it will validate and process the request, and these details will be 
                 presisted in **ETCD**

**ETCD** : It is a kind of Data base to k8s and K8s uses etcd to store the cluster data. The data stored in ETCD is in key-Value distrubuted type data store.
           It contains all the Info of Pods & Nodes. Some of the data stores in ETCD such as Job scheduling into Pods, state info etc..

**Scheduler** : Responsible for scheduling the pods to Nodes.
                Scheduler will verify the ETCD means Scheduler will check in ETCD & schedules the Nodes to Pods which are unscheduled & scheduler will decide which pod should deploy                      on which Node.
                It decides by communicating with Kubelet and identifies which Nodes has enough CPU & Memory, and also checks based on other policies such as taints & Tolerations & Node                   affinity rules etc.. So that it can schedule the pod.

 **Kubernetes Controller Manager** : It’s like a supervisor that constantly checks whether everything is working as expected. The Controller Manager has several "controllers," each                                            responsible for different tasks, such as making sure the right number of application copies (pods) are running, monitoring the health of machines                                          (nodes), and managing resources like jobs and services.
 
         **Node Controller** :Manages node operations. It is responsible for monitoring the health of nodes, detecting node  failures, 
                              and managing node lifecycles (e.g., adding/removing nodes from the cluster).
                                               
         **Replication Controller** :Ensures that a specified number of pod replicas are running at all times. If there are more or 
                                     fewer replicas than desired, it will create or delete pods to reach the desired number.
          

**Kubelet** : It is primary Node agent and runs on each and every Node and It works by continuously communicating with the Kubernetes API server, managing the containers through the                    container runtime, performing health checks, and ensuring the node's state is consistent with the desired state defined by Kubernetes. Without the kubelet, the Kubernetes                 cluster wouldn't be able to manage containers on individual nodes, making it a vital component for the orchestration of containers.

**Kubeproxy** : N/W proxy .If we want to access the containers wihtin the cluster or outside the cluster wiuth the help of Kubeproxy.
                Service is a logical concept but actual work will be done by Kubeproxy.This service ensures that necessary rules are in place.

           
                




   


