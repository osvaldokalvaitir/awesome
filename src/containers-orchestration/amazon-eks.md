# Amazon EKS

O Amazon Elastic Kubernetes Service (EKS) é um serviço gerenciado da AWS para executar o Kubernetes na nuvem e on-premises, sem precisar instalar e manter o plano de controle do cluster. A AWS cuida da disponibilidade, escalabilidade e atualizações do Kubernetes, e o serviço se integra a recursos como IAM, VPC, Elastic Load Balancing e Amazon ECR. Também oferece o EKS Auto Mode, que gerencia automaticamente os nós de computação, e o Amazon EKS Anywhere, para executar clusters na própria infraestrutura.

## Documentação e Acesso ao Serviço

Clique [aqui](https://aws.amazon.com/eks) para ver a documentação e acessar o serviço.

## Comandos

Os comandos abaixo usam o [eksctl](https://eksctl.io), CLI oficial para criar e gerenciar clusters no EKS, e a [AWS CLI](https://aws.amazon.com/cli).

Criar um cluster:

```
eksctl create cluster --name <nome_cluster> --region <regiao>
```

Listar os clusters:

```
eksctl get cluster --region <regiao>
```

Configurar o `kubectl` para acessar o cluster:

```
aws eks update-kubeconfig --name <nome_cluster> --region <regiao>
```

Excluir um cluster:

```
eksctl delete cluster --name <nome_cluster> --region <regiao>
```
