# ☁️ AWS Quest Learning Journey

## 📖 Sobre o Projeto

Este repositório reúne as atividades práticas desenvolvidas durante a trilha **AWS Quest**, abrangendo os principais serviços da Amazon Web Services (AWS).

O objetivo é consolidar conhecimentos em computação em nuvem por meio de laboratórios práticos envolvendo armazenamento, computação, redes, segurança, bancos de dados, escalabilidade, alta disponibilidade e arquitetura resiliente.

---

## 🎯 Objetivos da Jornada

- Desenvolver habilidades práticas na AWS
- Implementar soluções escaláveis e resilientes
- Aplicar conceitos de segurança em nuvem
- Trabalhar com bancos de dados relacionais e NoSQL
- Compreender estratégias de otimização de custos
- Construir um portfólio de projetos em Cloud Computing

---

# 📚 Laboratórios Realizados

## 1️⃣ Hospedagem de Sites Estáticos no Amazon S3

### Serviços Utilizados
- Amazon S3

### Objetivos
- Habilitar hospedagem estática
- Configurar permissões do bucket

### Principais Atividades
- Criação do bucket S3
- Renomeação do arquivo principal para `waves.html`
- Desativação do bloqueio de acesso público
- Aplicação de política JSON permitindo `s3:GetObject`

---

## 2️⃣ Primeiros Passos na Nuvem (EC2 e Script de Inicialização)

### Serviços Utilizados
- Amazon EC2
- Amazon S3

### Objetivos
- Implantar uma instância EC2
- Configurar User Data para automação

### Principais Atividades
- Download do script `user-data.txt`
- Criação de instância Amazon Linux 2023
- Configuração do Security Group para HTTP (porta 80)
- Automação da instalação e configuração do servidor web

---

## 3️⃣ Soluções de Computação (Gerenciamento de Instâncias)

### Serviços Utilizados
- Amazon EC2
- AWS Systems Manager

### Objetivos
- Realizar scale up de instâncias
- Utilizar Session Manager para administração

### Principais Atividades
- Consulta de metadados da instância
- Conexão sem chaves SSH utilizando Session Manager
- Alteração do tipo de instância de `t3.micro` para `m4.large`

---

## 4️⃣ Conceitos de Rede (VPC e Conectividade)

### Serviços Utilizados
- Amazon VPC
- Internet Gateway
- Security Groups

### Objetivos
- Configurar conectividade com a internet
- Aplicar regras de segurança

### Principais Atividades
- Revisão de endereços IP públicos e privados
- Associação de Internet Gateway
- Configuração de rota `0.0.0.0/0`
- Liberação das portas:
  - 80 (HTTP)
  - 3306 (MySQL)

---

## 5️⃣ Economias na Nuvem (Calculadora de Custos)

### Serviços Utilizados
- AWS Pricing Calculator

### Objetivos
- Estimar custos de infraestrutura

### Principais Atividades
- Definição de carga basal e picos de utilização
- Seleção de instâncias EC2
- Comparação entre modelos:
  - On-Demand
  - Reserved Instances
- Inclusão de custos de suporte e transferência de dados

---

## 6️⃣ Banco de Dados na Prática (RDS e Migração)

### Serviços Utilizados
- Amazon RDS
- AWS Database Migration Service (DMS)

### Objetivos
- Automatizar administração de banco de dados
- Implementar alta disponibilidade

### Principais Atividades
- Criação de banco MariaDB
- Configuração Multi-AZ
- Ativação de backups automáticos
- Implementação de réplicas de leitura

---

## 7️⃣ Conectando VPCs (VPC Peering)

### Serviços Utilizados
- Amazon VPC

### Objetivos
- Permitir comunicação privada entre VPCs

### Principais Atividades
- Criação da conexão de peering
- Aceitação da solicitação
- Atualização das tabelas de rotas
- Comunicação entre os ambientes de Marketing e Finanças

---

## 8️⃣ Primeiro Banco de Dados NoSQL (DynamoDB)

### Serviços Utilizados
- Amazon DynamoDB

### Objetivos
- Criar e consultar tabelas NoSQL

### Principais Atividades
- Criação da tabela com chave `UserId`
- Inserção de dados estruturados e semiestruturados
- Utilização de:
  - Query
  - Scan
- Filtragem de registros específicos

---

## 9️⃣ Conceitos Básicos de Segurança (IAM)

### Serviços Utilizados
- AWS Identity and Access Management (IAM)

### Objetivos
- Aplicar o princípio do menor privilégio

### Principais Atividades
- Criação do grupo `SupportEngineers`
- Associação da política `ReadOnlyAccess`
- Criação de usuários IAM
- Validação das restrições de acesso

---

## 🔟 Recuperação Automática e Escalabilidade (Auto Scaling)

### Serviços Utilizados
- Amazon EC2
- Auto Scaling
- Amazon CloudWatch

### Objetivos
- Automatizar a escalabilidade da infraestrutura

### Principais Atividades
- Criação de AMI personalizada
- Configuração de Launch Template
- Definição de capacidade:
  - Mínima
  - Desejada
  - Máxima
- Configuração de escalabilidade baseada em CPU

---

## 1️⃣1️⃣ Aplicativos Web de Alta Disponibilidade (Load Balancer)

### Serviços Utilizados
- Elastic Load Balancing (ELB)
- EC2 Auto Scaling

### Objetivos
- Distribuir carga e garantir alta disponibilidade

### Principais Atividades
- Criação de Target Group
- Configuração de Health Checks
- Implantação de Application Load Balancer (ALB)
- Integração com múltiplas Zonas de Disponibilidade

---

## 1️⃣2️⃣ Modernizar uma Arquitetura de Nuvem (Desafio Final)

### Objetivos
- Implementar uma arquitetura resiliente, segura e escalável

### Principais Atividades
- Ativação de Multi-AZ no Amazon RDS
- Criação da tabela `UrbanGo-ActivityLog`
- Aceitação de VPC Peering pendente
- Escalabilidade de instâncias EC2 em múltiplas AZs
- Ajuste das permissões IAM da função `AppRole`
- Validação de acesso ao DynamoDB

---

# 🛠️ Tecnologias Utilizadas

- Amazon S3
- Amazon EC2
- Amazon VPC
- AWS IAM
- AWS Systems Manager
- Amazon RDS
- AWS DMS
- Amazon DynamoDB
- Amazon CloudWatch
- Auto Scaling
- Elastic Load Balancing
- AWS Pricing Calculator

---

# 📈 Competências Desenvolvidas

✅ Cloud Computing

✅ Infraestrutura como Serviço (IaaS)

✅ Redes na AWS

✅ Segurança e IAM

✅ Bancos de Dados Relacionais

✅ Bancos de Dados NoSQL

✅ Escalabilidade Automática

✅ Alta Disponibilidade

✅ Monitoramento

✅ Otimização de Custos

✅ Arquiteturas Resilientes

---

# 🏆 Resultado

Ao finalizar esta jornada, foram aplicados conceitos fundamentais e avançados da AWS, abrangendo desde hospedagem de aplicações até arquiteturas altamente disponíveis, seguras e escaláveis, fortalecendo a experiência prática em Cloud Computing e preparação para certificações AWS.

---

**Autor:** Fabricio Silva de Oliveira  
**Certificação:** AWS Certified Cloud Practitioner ☁️
