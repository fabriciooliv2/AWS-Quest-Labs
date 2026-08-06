# 🌐 AWS Quest - Conceitos de Rede

## 📖 Descrição

Neste laboratório do AWS Quest, explorei os principais componentes de rede da AWS utilizando o Amazon VPC (Virtual Private Cloud). Durante a atividade, foram configuradas tabelas de rotas, Internet Gateway e Security Groups para permitir conectividade segura entre recursos da infraestrutura e a internet.

---

# 🎯 Objetivos do Laboratório

✅ Explorar os componentes que compõem uma Virtual Private Cloud (VPC).

✅ Compreender a relação entre VPC, sub-redes e tabelas de roteamento.

✅ Configurar rotas para acesso à internet.

✅ Analisar a função de um Internet Gateway.

✅ Configurar regras de entrada e saída em Security Groups.

✅ Controlar o acesso entre servidores web e banco de dados.

---

# 🏗️ Arquitetura da Solução

```text
🌎 Internet
     │
     ▼
🌐 Internet Gateway
     │
     ▼
🔀 Router
     │
 ┌───┴───────────────┐
 │                   │
 ▼                   ▼
🌍 Public Subnet     🔒 Private Subnet
10.10.0.0/24        10.10.2.0/24
 │                   │
🖥️ Web Server       🗄️ DB Server
 │                   │
🛡️ Security Group   🛡️ Security Group
```

A arquitetura demonstra a separação entre recursos públicos e privados dentro de uma VPC, garantindo maior segurança e controle de acesso.

---

# 🚀 Desenvolvimento da Atividade

## 1️⃣ Acesso ao Amazon EC2

O laboratório iniciou com o acesso ao serviço Amazon EC2 no Console AWS para identificar os recursos previamente provisionados.

Foram observadas duas instâncias:

- 🖥️ Web Server
- 🗄️ DB Server

<img width="1397" height="678" alt="01-console-ec2" src="https://github.com/user-attachments/assets/24330c6e-826d-4936-a96f-494090000b3a" />

---

## 2️⃣ Identificação do Web Server

Foi selecionada a instância Web Server para análise de suas configurações de rede.

Informações verificadas:

- Endereço IPv4 Público
- Endereço IPv4 Privado
- DNS Público
- Tipo da Instância
- Status da Instância

<img width="1398" height="678" alt="02-webserver-detalhes" src="https://github.com/user-attachments/assets/eb83cb8f-a6b1-4570-8f31-f4cece722b7c" />

---

## 3️⃣ Teste Inicial de Conectividade

Foi realizado um teste de acesso ao endereço IP público do servidor web.

### Resultado

❌ Falha na conexão.

O navegador apresentou erro de timeout, demonstrando que existiam restrições de conectividade que precisavam ser corrigidas durante o laboratório.

<img width="1400" height="676" alt="03-timeout-conexao" src="https://github.com/user-attachments/assets/67fc6784-6702-44cb-987f-ac1b2de55434" />

---

## 4️⃣ Análise das Configurações de Rede

Na aba Networking da instância foram analisados:

- IPV4 Público
- IPV4 Privado
- VPC associada
- Subnet associada

Foi identificado que o servidor estava localizado em uma VPC específica criada para o laboratório.

<img width="1397" height="677" alt="04-networking" src="https://github.com/user-attachments/assets/bf9a936f-766f-4b75-b01c-11c4bafc78c0" />

---

## 5️⃣ Exploração da Subnet

A partir da instância Web Server foi acessada a subnet associada.

Durante a análise foram observados:

- Subnet ID
- Availability Zone
- Intervalo de endereços IP
- Associação com a VPC

<img width="1393" height="674" alt="05-subnet" src="https://github.com/user-attachments/assets/838734d7-ba58-407b-bab8-5cb297b80cd5" />
<img width="1395" height="676" alt="05.1-subnet" src="https://github.com/user-attachments/assets/acf3cd04-1d81-4ef1-b4fa-dd750e12b563" />

---

## 6️⃣ Análise da Tabela de Rotas

Foi acessada a tabela de rotas associada à subnet.

As rotas identificadas inicialmente eram:

```text
10.10.0.0/16 → local
0.0.0.0/0 → NAT Gateway
```

Essas rotas determinavam como o tráfego era encaminhado dentro e fora da rede.

<img width="1401" height="676" alt="06-route-table" src="https://github.com/user-attachments/assets/688519aa-3417-447f-9f6b-11ba0b46764f" />
<img width="1395" height="683" alt="06.1-route-table" src="https://github.com/user-attachments/assets/1bc19392-7e65-4f33-8941-e7cdccbb08be" />

---

## 7️⃣ Alteração da Tabela de Rotas

Foi removida a rota que encaminhava o tráfego através do NAT Gateway.

Posteriormente foi criada uma nova rota:

```text
Destino: 0.0.0.0/0
Alvo: Internet Gateway
```

Essa alteração permitiu que a subnet se tornasse acessível diretamente pela internet.

<img width="1396" height="679" alt="07-internet-gateway" src="https://github.com/user-attachments/assets/6eb2ad84-31d3-434c-8e85-dd0aa2cf7539" />
<img width="1394" height="676" alt="07.1-internet-gateway" src="https://github.com/user-attachments/assets/d93ebdb7-cd0a-4a7b-923e-172d1ba10cca" />

---

## 8️⃣ Configuração do Security Group

Foi acessado o grupo de segurança associado ao servidor Web.

### Regra criada

```text
Type: HTTP
Protocol: TCP
Port: 80
Source: Anywhere-IPv4
```

Essa configuração permitiu o acesso HTTP ao servidor web a partir da internet.

<img width="1394" height="676" alt="08-inbound-rule-http" src="https://github.com/user-attachments/assets/916be8e0-2507-4c05-a8a6-19b154f97a42" />
<img width="1393" height="681" alt="08.1-inbound-rule-http" src="https://github.com/user-attachments/assets/4150a32b-96c7-44c6-ac8c-f1c253f6e820" />
<img width="1397" height="677" alt="08.2-inbound-rule-http" src="https://github.com/user-attachments/assets/cb7d2e19-37f5-4755-a49d-1767310a0e35" />
<img width="1402" height="681" alt="08.3-inbound-rule-http" src="https://github.com/user-attachments/assets/bd7faae6-9cb3-4e7c-b486-532c94136ebc" />

---

## 9️⃣ Análise das Regras de Saída

Foram verificadas as regras de saída existentes no Security Group.

Portas identificadas:

```text
80  → HTTP
443 → HTTPS
3306 → MySQL
```

Essas permissões permitem comunicação externa da instância com serviços web e banco de dados.

<img width="1395" height="677" alt="09-outbound-rules" src="https://github.com/user-attachments/assets/0c9d3c4a-96b2-46ff-9868-3be5ae1300fb" />
<img width="1397" height="676" alt="09.1-outbound-rules" src="https://github.com/user-attachments/assets/f6e87d54-9556-45e6-be85-762ba0dce449" />
<img width="1396" height="678" alt="09.2-outbound-rules" src="https://github.com/user-attachments/assets/4452d3ba-850d-48f7-bf09-bd2c5de36612" />
<img width="1392" height="676" alt="09.3-outbound-rules" src="https://github.com/user-attachments/assets/512f6fdd-24a8-4fb3-97a0-10ca4ae0466e" />

---

## 🔟 Validação da Conectividade

Após as alterações de roteamento e Security Groups, foi realizado novo teste utilizando o endereço IP público do servidor.

### Resultado

✅ O diagrama da arquitetura foi exibido corretamente.

✅ O servidor Web tornou-se acessível pela internet.

✅ Foi comprovada a comunicação através da infraestrutura configurada.

<img width="1397" height="677" alt="10-validacao-webserver" src="https://github.com/user-attachments/assets/83746fbf-a874-4d2f-930b-3b093f5d6401" />
<img width="1399" height="716" alt="10.1-validacao-webserver" src="https://github.com/user-attachments/assets/0e725d7f-448d-42a5-962d-699ece1588c3" />

---

# 🎯 Desafio (DIY)

## Objetivo

Alterar as regras do Security Group para permitir tráfego na porta **3306** para o servidor de banco de dados (DB Server).

### Situação Atual

O banco de dados encontra-se em uma subnet privada e sua comunicação é controlada por Security Groups.

### Ação Esperada

Adicionar uma regra de entrada permitindo comunicação MySQL através da porta:

```text
3306
```

Normalmente restringindo a origem ao grupo de segurança associado ao Web Server.

<img width="1478" height="782" alt="11-diy-porta-3306" src="https://github.com/user-attachments/assets/0ccf56cd-afaa-4474-9fbc-e028369844b2" />

---

# 📂 Estrutura das Evidências

```text
evidencias/
│
├── 01-console-ec2.png
├── 02-webserver-detalhes.png
├── 03-timeout-conexao.png
├── 04-networking.png
├── 05-subnet.png
├── 06-route-table.png
├── 07-internet-gateway.png
├── 08-inbound-rule-http.png
├── 09-outbound-rules.png
├── 10-validacao-webserver.png
└── 11-diy-porta-3306.png
```

---

# 🛠️ Serviços AWS Utilizados

- ☁️ Amazon EC2
- 🌐 Amazon VPC
- 🔀 Route Tables
- 🌍 Internet Gateway
- 🛡️ Security Groups
- 📡 Subnets
- 🌎 IPv4 Networking

---

# 📚 Conhecimentos Adquiridos

Durante este laboratório foram reforçados conceitos relacionados a:

- Arquitetura de rede na AWS.
- Virtual Private Cloud (VPC).
- Sub-redes públicas e privadas.
- Internet Gateway.
- NAT Gateway.
- Tabelas de roteamento.
- Controle de acesso através de Security Groups.
- Comunicação entre servidores Web e Banco de Dados.
- Segurança de infraestrutura em nuvem.

---

# ✅ Conclusão

Este laboratório proporcionou uma experiência prática sobre os fundamentos de rede na AWS. Através da configuração de VPC, subnets, rotas e Security Groups, foi possível compreender como controlar o tráfego entre recursos internos e a internet. Além disso, a atividade demonstrou a importância da segmentação de rede e das políticas de segurança para proteger aplicações e bancos de dados em ambientes de nuvem, consolidando conhecimentos essenciais para arquiteturas AWS seguras e escaláveis.

---

## 🏷️ Tags

`AWS` `AmazonVPC` `Networking` `CloudComputing` `AWSQuest` `AWSSkillBuilder` `InternetGateway` `SecurityGroups` `RouteTables` `Infrastructure`
