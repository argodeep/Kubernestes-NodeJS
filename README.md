`kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml`
Check Cluster
`kubectl get services`

## Add worked Nodes
`kubeadm token create --print-join-command`
copy join command and run on worker node.

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
`curl http://[worker_node_ip]:8001`
