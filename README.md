# Kubernetes tutorial

## Initiate cluster
`kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.5.0.0/16`

## Initiate cluster networking
`kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml`

## Check Cluster
`kubectl get services`

## Add worked Nodes
on master node type
`kubeadm token create --print-join-command`
copy join command and run on worker node.
`kubeadm join 192.168.0.8:6443 --token l7gp41.a0gladucnijtttrx     --discovery-token-ca-cert-hash sha256:7615630ac430e503b716240303667ae12231fcc88b9d7c79e16c65a16dfe1bb6`

## Verify Worker Node
`kubectl get nodes`

## Create Deployment to Kubernetes
`kubectl create deployment demo --image=gcr.io/google-samples/kubernetes-bootcamp:v1`

## Check deployment
`kubectl get deployments`

## Check pods
`kubectl get pods`

## Expose
`kubectl expose deployment/demo --type="NodePort" --port=8001 --name="demo`

## Test
`curl http://[CLUSTER-IP]:8001`
