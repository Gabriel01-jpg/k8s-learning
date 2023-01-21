Kubernetes = Início da jornada.

Container = Container é o isolamento de recursos, processos e acessos. Não sendo o mesmo que máquina virtual, mesmo sendo parecido, pois a máquina virtual simula todo um novo SO, gerando simulação dos hardwares, enquanto o container utiliza o mesmo kernel que o host utilizando apenas o mínimo possível e isolando os recursos...

Mas o que é container engine? 

Container engine é o responsável fazer a criação do container e garantir que está devidamente isolado, fazer pontos de montagem, volumes, redes... 

E o container runtime?

É o responsável pela comunicação com os nós, ou seja, garantir a execução do container, usando cgroups, namespace... Sendo classificado em alguns tipos, como por exemplo:
    - Low-level: containers executados diretamente pelo kernel, como o runc, o crun e o runsc.
    - High-level: containers executados por um Container Engine, como o containerd.

# Kubernetes

- Kubernetes é um orquestrador de containers, responsável por organizar, orquestrar e gerenciar os containers...

## Arquitetura do K8S

Control plane - Tudo aquilo para gerenciar os clusters

Workers - Tudo que vai carregar as aplicações


Componentes do control plane:
    - etcd -> é o datastore que guarda todo o estado do cluster
    - kube apiserver -> conversa com todo o cluster, que tem como função gerenciar toda comunicação e guardar informações no etcd
    - kube scheduler -> responsável por gerenciar local onde vai rodar os containers e controlar nós e pods...
    - kube controller manager -> 


Componentes do workers:
    - kubelet -> é o agent, verifica se está tudo rodando normal
    - kube proxy -> comunicação dos pods com o resto do mundo



Portas que rodam:
    kube-apiserver => 6443 -> TCP
    etcd => 2379-2380 -> TCP
    kubelet -> 10250 -> TCP
    kube-scheduler => 10251 -> TCP
    kube-controller => 10252 -> TCP


nodeport -> 30000 - 32767 - TCP
weave net -> 6783/6784 -> TCP/UDP

## Arroz com feijão do Kubernetes

1º -> Menor gerenciamento vai ser pod, diferencia de container pois pode ter um ou mais container.

## POD
    - Contém somente um IP
    - Um isolamento
    - Pode ter mais de um container e compartilha o universo com todos


## Deployment
    - Um dos principais controllers utilizados
    - Responsável por gerenciar o ciclo de vida das aplicações
    - 