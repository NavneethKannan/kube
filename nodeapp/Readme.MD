### YAML files for a simple node app

contains yaml files for a simple node app which can be found at https://github.com/nakmonster/node-cluster-kubernetes and https://github.com/icecreamsandwich/node-cluster-kubernetes

#####	deploy-nodes.yml

- unified file for all the deployments (master-deploy.yml, slave-deploy.yml, slave2-deploy.yml)

##### master-deploy.yml

- single replica deployment of the image '192.168.1.220:5000/node_master'. has two environment variables that point to the node_slave's and node_slave2's services.

##### master-service.yml

- simple NodePort service that exposes 30000 port on the node and links it with 5001 port of pods/depployment that match label 'app: master-deploy'

##### service-nodes.yml

- unified file for all the services (master-service.yml, slave-service.yml, slave2-service.yml)

##### slave-service.yml and slave2-service.yml

- services of default kind(clusterIP) that exposes 5002, 5003 ports to the cluster network and links it with respective pods/deployment

##### slave-deploy.yml and slave2-deploy.yml

- single replica deployment that matches the label 'slave2-deploy'/'slave-deploy' and exposes port 5003/5002 respectively. Created form image node_slave and node_slave2 from the local docker registry.
