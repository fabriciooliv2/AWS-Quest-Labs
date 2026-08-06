# 💰 AWS Quest - Economias na Nuvem

## 📖 Descrição

Neste laboratório do AWS Quest, explorei o uso do AWS Pricing Calculator para criar estimativas de custo de uma arquitetura baseada em Amazon EC2. Durante a atividade, foram analisados modelos de cobrança da AWS, opções de otimização de custos, armazenamento Amazon EBS, transferência de dados e estratégias de escalabilidade para cargas de trabalho variáveis.

---

# 🎯 Objetivos do Laboratório

✅ Criar grupos lógicos de preços.

✅ Construir uma estimativa de custos utilizando o AWS Pricing Calculator.

✅ Configurar uma carga de trabalho baseada em picos de demanda.

✅ Comparar opções de compra do Amazon EC2.

✅ Avaliar custos de armazenamento e transferência de dados.

✅ Gerar estimativas para tomada de decisão antes de implementar recursos na AWS.

---

# 🏗️ Cenário Proposto

O laboratório simulou um ambiente web hospedado em instâncias Amazon EC2 com escalabilidade baseada em demanda.

```text
👥 Usuários
      │
      ▼
⚖️ Auto Scaling Group
      │
 ┌────┴────┐
 ▼         ▼
🖥️ EC2     🖥️ EC2
t3.medium  t3.medium
      │
      ▼
☁️ AWS Cloud
```

O objetivo foi estimar os custos mensais e anuais dessa arquitetura antes de sua implementação.

---

# 🚀 Desenvolvimento da Atividade

## 1️⃣ Acesso ao AWS Pricing Calculator

A atividade iniciou com o acesso ao serviço:

```text
https://calculator.aws
```

Foi criada uma nova estimativa para modelar os custos da solução proposta.

<img width="1399" height="707" alt="01-pricing-calculator" src="https://github.com/user-attachments/assets/56cedc6e-6e28-43a4-94bd-faf8ed3e6723" />
<img width="1392" height="677" alt="01.1-pricing-calculator" src="https://github.com/user-attachments/assets/ebe5d838-7acd-4e52-abf9-54919fdda810" />

---

## 2️⃣ Criação de Grupo de Estimativa

Foi criado um agrupamento lógico para organizar os custos da solução.

### Grupo criado

```text
Web Servers
```

Esse recurso facilita a organização e comparação entre diferentes cenários de infraestrutura.

<img width="1397" height="679" alt="02-grupo-web-servers" src="https://github.com/user-attachments/assets/52173f8e-115f-410f-8f7f-ba8061c27d2a" />
<img width="1393" height="674" alt="02.1-grupo-web-servers" src="https://github.com/user-attachments/assets/05f62093-be1d-4d18-9ed3-d6da123a72a1" />

---

## 3️⃣ Adição do Serviço Amazon EC2

Foi adicionada uma estimativa para o serviço Amazon EC2.

### Configurações iniciais

- Serviço: Amazon EC2
- Região: US East (N. Virginia)
- Sistema Operacional: Linux
- Tenancy: Shared Instances

Essas configurações serviram como base para o cálculo dos custos operacionais da infraestrutura.

<img width="1393" height="672" alt="03-configuracao-ec2" src="https://github.com/user-attachments/assets/bb4e7ece-dee1-46d2-a35b-e33b63a52c27" />
<img width="1393" height="669" alt="03.1-configuracao-ec2" src="https://github.com/user-attachments/assets/87690425-91cc-4c49-8b83-0d688d1eae62" />
<img width="1392" height="673" alt="03.2-configuracao-ec2" src="https://github.com/user-attachments/assets/d1a48993-aa0d-4fc6-868f-86f011b7d143" />
<img width="1398" height="724" alt="03.3-configuracao-ec2" src="https://github.com/user-attachments/assets/0519135b-47d3-4881-b8cd-d7515c412902" />

---

## 4️⃣ Configuração da Carga de Trabalho

Foi selecionado o perfil:

```text
Daily Spike Traffic
```

Com os seguintes parâmetros:

### Linha de Base

```text
2 instâncias
```

### Pico de Utilização

```text
4 instâncias
```

### Duração do Pico

```text
8 horas por dia
```

### Dias de Operação

```text
Domingo a Sábado
```

Esse cenário representa aplicações que recebem aumento diário de tráfego em horários específicos.

<img width="1396" height="675" alt="04-workload-configurada" src="https://github.com/user-attachments/assets/5a447d30-e77f-4fd0-a8e1-d6f54548a2e9" />
<img width="1393" height="674" alt="04.1-workload-configurada" src="https://github.com/user-attachments/assets/bd607d3d-cb27-4586-8bf3-d8caa7763b60" />

---

## 5️⃣ Seleção da Instância EC2

A infraestrutura foi configurada utilizando:

```text
t3.medium
```

### Especificações

- 2 vCPUs
- 4 GiB de memória
- EBS Only

O AWS Pricing Calculator permitiu comparar diferentes alternativas antes da escolha final da instância.

<img width="1396" height="676" alt="05-instancia-t3-medium" src="https://github.com/user-attachments/assets/452dac5c-066a-44c7-ae96-064f1a149e2b" />

---

## 6️⃣ Opções de Compra

Foram analisados os principais modelos de cobrança da AWS:

### 💳 On-Demand

Pagamento conforme uso.

### 📉 Savings Plans

Descontos mediante compromisso de utilização.

### 📦 Reserved Instances

Reservas por períodos de 1 ou 3 anos.

### ⚡ Spot Instances

Utilização da capacidade ociosa da AWS com descontos significativos.

<img width="1387" height="709" alt="06-opcoes-compra" src="https://github.com/user-attachments/assets/60754e3e-9db4-4062-851e-c2e5d141ec47" />
<img width="1397" height="723" alt="06.1-opcoes-compra" src="https://github.com/user-attachments/assets/499fdd9b-f07d-4514-a542-7300c050a6ed" />

---

## 7️⃣ Análise da Utilização Mensal

O cálculo demonstrou como as instâncias são cobradas de acordo com a utilização.

### Resultado observado

- Instâncias de base executando 24 horas por dia.
- Instâncias adicionais utilizadas apenas durante os horários de pico.

### Total calculado

```text
1946,66 horas mensais
```

Essa modelagem demonstra como a elasticidade da nuvem reduz desperdícios e melhora a eficiência de custos.

<img width="1395" height="697" alt="07-utilizacao-mensal" src="https://github.com/user-attachments/assets/383fe725-e7f7-4159-a6ad-47e00950dcb7" />

---

## 8️⃣ Configuração do Amazon EBS

Foi adicionada camada de armazenamento para cada instância.

### Configurações

```text
Tipo: General Purpose SSD (gp3)
Capacidade: 10 GB
IOPS: 30
```

Também foi habilitada a utilização de snapshots para backup dos volumes.

<img width="1391" height="706" alt="08-ebs-configurado" src="https://github.com/user-attachments/assets/aff6c978-823b-4c34-bbe5-f1025a5683c4" />

---

## 9️⃣ Configuração de Snapshots

### Configuração aplicada

```text
Frequência: Weekly
Alteração por Snapshot: 1 GB
```

Essa configuração permitiu estimar os custos relacionados à retenção e proteção dos dados armazenados nos volumes EBS.

<img width="1396" height="677" alt="09-snapshots" src="https://github.com/user-attachments/assets/09023038-4f01-4d11-93a8-41d05bd3b417" />

---

## 🔟 Transferência de Dados

Foi realizada a estimativa de transferência de dados para entrada e saída da infraestrutura.

### Entrada

```text
Internet → AWS
1 TB/mês
```

### Saída

```text
AWS → Internet
100 GB/mês
```

O cálculo demonstrou que transferências de entrada normalmente não geram cobrança, enquanto transferências de saída impactam o custo final da solução.

<img width="1399" height="677" alt="10-data-transfer" src="https://github.com/user-attachments/assets/b8fdb9e9-a837-44bf-99d8-719616b59488" />

---

## 1️⃣1️⃣ Resultado da Estimativa

Após consolidar todos os recursos, foi gerada a estimativa final da solução.

### Custos calculados

```text
Upfront Cost: USD 0.00

Monthly Cost: USD 93.66

12 Months Cost: USD 1,123.92
```

A estimativa forneceu uma visão detalhada dos custos previstos para operação da arquitetura proposta.

<img width="1393" height="675" alt="11-estimativa-final" src="https://github.com/user-attachments/assets/2dfd0a5b-37ec-496a-84cd-0a76c52138a4" />

---

## 1️⃣2️⃣ Compartilhamento da Estimativa

O AWS Pricing Calculator permitiu gerar um link público para compartilhar a estimativa com outras equipes ou partes interessadas.

### Benefícios

- Compartilhamento de propostas.
- Revisão técnica.
- Aprovação financeira.
- Planejamento de infraestrutura.

<img width="1394" height="671" alt="12-link-publico" src="https://github.com/user-attachments/assets/e2ebe9c7-fde1-4531-be2e-0cc8f890c5a3" />
<img width="1393" height="676" alt="12.1-link-publico" src="https://github.com/user-attachments/assets/1a875587-8c98-4c18-88cf-5b03bdd6bddc" />
<img width="1394" height="672" alt="12.2-link-publico" src="https://github.com/user-attachments/assets/62849967-947a-4629-9f48-5ce47643091d" />

---

# 🎯 Desafio (DIY)

## Objetivo

Modificar a estimativa criada alterando o tipo de instância Amazon EC2.

### Situação Inicial

```text
t3.medium
```

### Situação Solicitada

```text
t2.micro
```

Após a alteração, uma nova estimativa deveria ser gerada e compartilhada através de um novo link público do AWS Pricing Calculator.

<img width="1483" height="786" alt="13-diy-t2-micro" src="https://github.com/user-attachments/assets/c7a0b0ab-98c3-4d2a-a532-9705c577044b" />

---

# 📂 Estrutura das Evidências

```text
evidencias/
│
├── 01-pricing-calculator.png
├── 02-grupo-web-servers.png
├── 03-configuracao-ec2.png
├── 04-workload-configurada.png
├── 05-instancia-t3-medium.png
├── 06-opcoes-compra.png
├── 07-utilizacao-mensal.png
├── 08-ebs-configurado.png
├── 09-snapshots.png
├── 10-data-transfer.png
├── 11-estimativa-final.png
├── 12-link-publico.png
└── 13-diy-t2-micro.png
```

---

# 🛠️ Serviços AWS Utilizados

- 💰 AWS Pricing Calculator
- ☁️ Amazon EC2
- 💾 Amazon EBS
- 📸 Amazon EBS Snapshots
- 📊 AWS Cost Estimation Tools

---

# 📚 Conhecimentos Adquiridos

Durante este laboratório foram praticados conceitos relacionados a:

- Planejamento financeiro em nuvem.
- Modelagem de custos AWS.
- Elasticidade e escalabilidade.
- Opções de compra EC2.
- Savings Plans.
- Reserved Instances.
- Spot Instances.
- Armazenamento Amazon EBS.
- Transferência de dados.
- Otimização de custos na AWS.

---

# ✅ Conclusão

Este laboratório proporcionou uma visão prática sobre o planejamento financeiro de soluções em nuvem utilizando o AWS Pricing Calculator. A atividade demonstrou como estimar custos antes da implementação, avaliar diferentes modelos de compra do Amazon EC2, calcular despesas relacionadas a armazenamento e transferência de dados, além de aplicar conceitos de elasticidade para reduzir desperdícios. O desafio final reforçou a importância do dimensionamento adequado dos recursos ao substituir a instância **t3.medium** por **t2.micro**, evidenciando como pequenas alterações de arquitetura podem impactar diretamente os custos operacionais da solução.

---

## 🏷️ Tags

`AWS` `AmazonEC2` `AWSPricingCalculator` `CloudEconomics` `CostOptimization` `CloudComputing` `AWSQuest` `AWSSkillBuilder` `FinOps` `AmazonEBS`
