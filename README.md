# AWS Elastic Architecture: Auto Scaling & Load Balancing

## 📋 Sobre o Projeto
Este projeto demonstra a implementação de uma infraestrutura em nuvem na AWS capaz de se adaptar automaticamente a variações de tráfego. O objetivo principal foi garantir que a aplicação permanecesse disponível e performática mesmo sob alta carga de processamento.

## 🏗️ Arquitetura
A solução foi desenhada seguindo as melhores práticas de alta disponibilidade, distribuindo recursos em múltiplas Zonas de Disponibilidade (AZs).

![Diagrama da Arquitetura](./img/arquitetura.jpg) 
*(Referência:)*

## 🚀 Tecnologias e Serviços Utilizados
* **Amazon EC2**: Instâncias Linux para hospedar o servidor web.
* **AWS CLI**: Utilizada para automação, criação de instâncias e manipulação de AMIs.
* **Application Load Balancer (ALB)**: Responsável por distribuir o tráfego de entrada entre as instâncias saudáveis.
* **Auto Scaling Group**: Configurado para gerir o ciclo de vida das instâncias, com capacidade mínima de 2 e máxima de 4 servidores.
* **Amazon CloudWatch**: Utilizado para monitorizar métricas de CPU e disparar alarmes de escalonamento.

## 🛠️ Implementação Passo a Passo

1.  **Criação da Imagem Base (AMI)**: Através da AWS CLI, foi configurada uma instância padrão e criada uma Amazon Machine Image (AMI) para servir de template para o escalonamento.
2.  **Configuração do Load Balancer**: Implementação do ALB e definição dos Target Groups. O sistema foi validado com o status **"Integro"**, confirmando que o tráfego está a ser direcionado corretamente.
3.  **Definição de Políticas de Escalonamento**: Configuração do Auto Scaling para adicionar novas instâncias sempre que a utilização média de CPU ultrapassar 50%.
4.  **Teste de Stress**: Execução de um script de carga para forçar o aumento de CPU e validar o nascimento de novas instâncias em tempo real.

## 📈 Resultados
Durante os testes, o grupo de Auto Scaling respondeu com sucesso ao aumento de demanda, elevando o número de instâncias ativas e garantindo que a aplicação não ficasse indisponível.# aws-auto-scaling-lab
Implementação de uma arquitetura escalável e resiliente na AWS utilizando EC2, Application Load Balancer e Auto Scaling.
