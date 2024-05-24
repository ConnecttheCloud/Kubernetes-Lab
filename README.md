# Kubernetes Lab Practises 

This is my lab practise and you can view details contents in https://clouddays.info


## Installation and K8 cluster setup in GCloud

Subscribe GCloud as free subscription and create 2VMs for K8 master and worker node. 

This lab is using G Cloud free tier subscribtions.


### Create VMs

#### Master Node 
```
1. Master node VM:
name: master
family: e2-medium (2vCPU, 4GB)
image: ubuntu20.04 LTS 
disk: 50GB
```

#### Worker Node
````
2. Worker node VM:
name: worker1
family: e2-medium (2vCPU, 4GB)
image: ubuntu20.04
disk: 50GB
````

### Install GCloud CLI tool

https://cloud.google.com/sdk/docs/install 

Follow this link for GCloud Installation. 

#### GCLoud CLI configuration (Powershell)
```
set-alias g gcloud

# Connect to GCloud
g auth login
g projects list
g config set project <project_name>

# SSH into VMs from GCLI
g compute instances list
g compute ssh master


## K8 Cluster Installation

Launch Powershell to access master
```
g compute ssh master
sudo -i

curl -s 


-------------------------------------------------------------------

g computer ssh worker1

sudo -i

curl -s
```





## Open FW ports for NodePort SVC

```
gcloud compute firewall-rules create nodeports --allow tcp:30000-40000
```