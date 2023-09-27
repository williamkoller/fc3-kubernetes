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