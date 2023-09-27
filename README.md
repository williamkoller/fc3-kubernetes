# Kubernetes

### Pontos importantes

- Kubernetes eh disponibilizado atraves de um conjunto de APIs
- Normalmente acessamos a API usando o CLI: kubectl
- Tudo eh baseado em estado. Voce configura o estado de cada objeto
- Kubernetes Master
  - Kube-apiserver
  - Kube-controller-manager
  - Kube-scheduler
- Outros Nodes:

  - Kubelet
  - Kubeproxy

- Cluster: conjunto de maquinas (Nodes)
- Cada maquina possui uma quantidade de vCPU e memoria
- Pods: unidade que contem os containers provisionados
- O Pod representa os processos rodando no cluster

### Deployment

- Objetivo de provisionar os pods

### Instalar [Kind](https://kind.sigs.k8s.io/)

#### Create Cluster

- `kind create cluster`

#### Connect cluster of kind

- `kubectl cluster-info --context kind-kind`

#### See if it's running

- `kubectl get nodes`

#### Create cluster multi-node

- `kind create cluster --config=k8s/kind.yaml --name=fullcycle`

#### Delete cluster

- `kind delete clusters 'name'`

#### View config cluster

- `kube config get-clusters`

#### Change config

- `kube config use-context kind-fullcycle`

#### Docker build

- `docker build -t williamkoller/hello-go .`

#### Docker run

- `docker run --rm -p 80:80 williamkoller/hello-go`

#### Docker push

- `docker push williamkoller/hello-go`

#### Apply Pod

- `kube apply -f k8s/pod.yaml`

#### Get Pod

- `kube get pod`

#### Redirect port

- `kube port-forward pod/goserver 8000:80`

#### View replicasets

- `kube get replicasets`

#### Describe Pod

- `kube describe pod goserver-4gtdw`

#### Rollout

- `kube rollout history deployment goserver`
- rollout last version `kube rollout undo deployment goserver`
- `kube rollout undo deployment goserver --to-revision=2`

#### Historic deployment

- `kube describe deployment`