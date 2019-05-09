### YAML file for mojolicious app

##### ldap-endpoint.yml

- endpoint and service for ldap server. Creates an endpoint ldap which points to 192.168.1.198:389. Also creates a service that links to this endpoint and exposes 389 port to cluster network.

##### mojo-deploy.yaml

- deployment of two replicas created from the image 192.168.1.220:5000/mojovm. Exposes port 3000 and matches label 'app: mojovm'.

##### mojo-service.yml

- NodePort service that exposes 30000 port on the node and links it with 3000 port of the required deployment/pods
