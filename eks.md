# EKS
## eks

### kube config dir and file

	vi .kube/config

### update kube cluster

	aws eks update-kubeconfig --name Cluster-Name --region us-west-2
	aws eks update-kubeconfig --name Cluster-Name --region eu-central-1

### Get kube config view

	kubectl config view

### Get kube cluster info
	
	kubectl cluster-info\n

### Get current context

	kubectl config current-context

### install kubectl on mac

	brew install kubectl

### Get all pods from cluster

	kubectl get pod -A -o wide |grep ip

### Get nodes from a cluster

	kubectl get node

### Get logs from a pod

	kubectl log kube-proxy

### Cordon a host/node

	kubectl cordon host

### get number container from namespace ec2

	kpg -n ec2 | grep Container | wc -l

### get 
	aws sts get-caller-identity

### Delete a pod

	kubectl delete pod 31h0vs-6bdf5f8b7b-c9zj4 --grace-period=0 --force --namespace ec2

### Get all pods in cluster

	kubectl get pod -o=custom-columns=NODE:.spec.nodeName,NAME:.metadata.name --all-namespaces |sort

### Useful alias for kube

k=kubectl
kaf='kubectl apply -f'
kca='_kca(){ kubectl "$@" --all-namespaces;  unset -f _kca; }; _kca'
kccc='kubectl config current-context'
kcdc='kubectl config delete-context'
kcgc='kubectl config get-contexts'
kcn='kubectl config set-context --current --namespace'
kcp='kubectl cp'
kcsc='kubectl config set-context'
kcuc='kubectl config use-context'
kdcj='kubectl describe cronjob'
kdcm='kubectl describe configmap'
kdd='kubectl describe deployment'
kdds='kubectl describe daemonset'
kdel='kubectl delete'
kdelcj='kubectl delete cronjob'
kdelcm='kubectl delete configmap'
kdeld='kubectl delete deployment'
kdelds='kubectl delete daemonset'
kdelf='kubectl delete -f'
kdeli='kubectl delete ingress'
kdelno='kubectl delete node'
kdelns='kubectl delete namespace'
kdelp='kubectl delete pods'
kdelpvc='kubectl delete pvc'
kdels='kubectl delete svc'
kdelsa='kubectl delete sa'
kdelsec='kubectl delete secret'
kdelss='kubectl delete statefulset'
kdi='kubectl describe ingress'
kdno='kubectl describe node'
kdns='kubectl describe namespace'
kdp='kubectl describe pods'
kdpvc='kubectl describe pvc'
kds='kubectl describe svc'
kdsa='kubectl describe sa'
kdsec='kubectl describe secret'
kdss='kubectl describe statefulset'
kecj='kubectl edit cronjob'
kecm='kubectl edit configmap'
ked='kubectl edit deployment'
keds='kubectl edit daemonset'
kei='kubectl edit ingress'
keno='kubectl edit node'
kens='kubectl edit namespace'
kep='kubectl edit pods'
kepvc='kubectl edit pvc'
kes='kubectl edit svc'
kess='kubectl edit statefulset'
keti='kubectl exec -ti'
kfkubeconfigeu='aws eks update-kubeconfig --name APOLLO-KF-EUC1-PRD --region eu-central-1'
kfkubeconfigus='aws eks update-kubeconfig --name APOLLO-KF-EUC1-PRD --region us-west-2'
kga='kubectl get all'
kgaa='kubectl get all --all-namespaces'
kgcj='kubectl get cronjob'
kgcm='kubectl get configmaps'
kgcma='kubectl get configmaps --all-namespaces'
kgd='kubectl get deployment'
kgda='kubectl get deployment --all-namespaces'
kgds='kubectl get daemonset'
kgi='kubectl get ingress'
kgia='kubectl get ingress --all-namespaces'
kgn='kubectl get node'
kgno='kubectl get nodes'
kgns='kubectl get namespaces'
kgp='kubectl get pods'
kgpa='kubectl get pods --all-namespaces'
kgpall='kubectl get pods --all-namespaces -o wide'
kgpns='kubectl get pods --all-namespaces'
kgpvc='kubectl get pvc'
kgpvca='kubectl get pvc --all-namespaces'
kgrs='kubectl get rs'
kgs='kubectl get svc'
kgsa='kubectl get svc --all-namespaces'
kgsec='kubectl get secret'
kgseca='kubectl get secret --all-namespaces'
kgss='kubectl get statefulset'
kgssa='kubectl get statefulset --all-namespaces'
kl='kubectl logs'
kl1h='kubectl logs --since 1h'
kl1m='kubectl logs --since 1m'
kl1s='kubectl logs --since 1s'
klf='kubectl logs -f'
klf1h='kubectl logs --since 1h -f'
klf1m='kubectl logs --since 1m -f'
klf1s='kubectl logs --since 1s -f'
klogs='kubectl logs'
kpf='kubectl port-forward'
krh='kubectl rollout history'
krsd='kubectl rollout status deployment'
krsss='kubectl rollout status statefulset'
kru='kubectl rollout undo'
ksd='kubectl scale deployment'
ksss='kubectl scale statefulset'
pakubeconfigeu='aws eks update-kubeconfig --name APOLLO-PA-EUC1-PROD --region eu-central-1'
pakubeconfigus='aws eks update-kubeconfig --name APOLLO-PA-USW2-PROD --region us-west-2'
