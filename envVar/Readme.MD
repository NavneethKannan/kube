### Busybox yaml files

##### busybox.yaml

- a simple busybox instance that will created as a Pod in the kubernetes cluster. 

##### env-deploy.yml

- a deployment with label 'app: env-deploy'. Created from the docker image '192.168.1.220:5000/newbusybox' . creates 2 pods (replicas) of this image.

##### env-pod.yml

- a pod with image 192.168.1.220:5000/newbusybox and environment variable NAME
