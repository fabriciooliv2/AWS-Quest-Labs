# ☁️ AWS Quest - Soluções de Computação

## 📖 Descrição

Neste laboratório do AWS Quest, explorei os principais recursos de computação da AWS utilizando o Amazon EC2. Durante a atividade, foram analisados diferentes tipos de instâncias, métodos de conexão, acesso a metadados e operações de gerenciamento de instâncias, culminando no redimensionamento de uma instância para um tipo mais robusto.

---

# 🎯 Objetivos do Laboratório

✅ Identificar e comparar tipos de instâncias Amazon EC2.

✅ Compreender as características das diferentes famílias de instâncias.

✅ Conectar-se a uma instância EC2 utilizando o EC2 Instance Connect.

✅ Consultar informações de metadados da instância.

✅ Iniciar e interromper instâncias EC2.

✅ Realizar o redimensionamento de uma instância para melhorar sua capacidade computacional.

---

# 🏗️ Arquitetura da Solução

```text
👤 Usuário
    │
    ▼
🌐 Navegador Web
    │
    ▼
☁️ Amazon EC2
    ├── 📋 Instance Metadata
    ├── 🔐 EC2 Instance Connect
    └── ⚙️ AWS Systems Manager
```

---

# 🚀 Desenvolvimento da Atividade

## 1️⃣ Acesso ao Amazon EC2

A atividade iniciou com o acesso ao serviço Amazon EC2 através do Console AWS, onde foi possível visualizar a instância disponibilizada pelo laboratório e analisar suas principais informações, como endereço IP, DNS público e tipo da instância.

<img width="1399" height="673" alt="Image" src="https://github.com/user-attachments/assets/beb2da6f-2960-4974-b423-6ed6126be837" />

---

## 2️⃣ Análise dos Tipos de Instância

Foram analisados diferentes tipos de instâncias EC2 para compreender suas características e aplicações:

- 🖥️ t3.large
- ⚡ c5.large
- 🧠 r5.large

Durante a comparação foram observadas diferenças de recursos computacionais, memória, desempenho de rede e custos operacionais.

<img width="1397" height="676" alt="Image" src="https://github.com/user-attachments/assets/3305bf11-80e6-4d5e-babb-6cd7fcc39dc1" />

---

## 3️⃣ Consulta aos Metadados da Instância

Através do endereço disponibilizado pela instância foi possível acessar informações de metadados importantes para administração e automação de ambientes em nuvem.

Foram identificados:

- Instance ID
- Instance Type
- Instance Family
- Availability Zone
- Endereço IP Público
- Endereço IP Privado 

<img width="1392" height="676" alt="Image" src="https://github.com/user-attachments/assets/6776fe9f-3154-4768-b640-dcb9975ff35f" />

---

## 4️⃣ Conexão com a Instância

Foi utilizada a funcionalidade **EC2 Instance Connect**, permitindo acesso seguro à instância Linux diretamente pelo navegador sem necessidade de configuração manual de chaves SSH.

<img width="1394" height="680" alt="Image" src="https://github.com/user-attachments/assets/550bdcf4-b9a6-4708-a72f-4d138e57988e" />
<img width="1396" height="675" alt="Image" src="https://github.com/user-attachments/assets/9641cc35-57f3-4de8-9899-211573756cde" />
<img width="1396" height="675" alt="Image" src="https://github.com/user-attachments/assets/5b23b0c0-686c-482b-9afa-94cd4211df2a" />
<img width="1394" height="723" alt="Image" src="https://github.com/user-attachments/assets/1d844c46-f237-4f00-98a6-54cb124edccd" />

---

## 5️⃣ Exploração da Aplicação

Após a conexão com a instância, foi realizado acesso ao diretório da aplicação para consultar seus arquivos e registros de execução.

### Comandos utilizados

```bash
cd sample_app
```

```bash
ls
```

```bash
tail -f aws_compute_solutions.log
```

Os logs permitiram visualizar informações relacionadas à própria instância EC2, incluindo tipo da instância, família e zona de disponibilidade.

<img width="1404" height="682" alt="Image" src="https://github.com/user-attachments/assets/883fafd0-1356-493b-8821-c954e2eef786" />

---

## 6️⃣ Gerenciamento da Instância

Foi realizada a interrupção da instância utilizando as opções disponíveis no Console AWS.

### Procedimento

```text
Instance State
   └── Stop Instance
```

Após a parada da instância foi possível observar a remoção temporária das informações de IP público e DNS público, confirmando o estado **Stopped**.

<img width="1400" height="681" alt="Image" src="https://github.com/user-attachments/assets/eb228856-37ca-4d34-97fd-e2cad92a204d" />
<img width="1394" height="677" alt="Image" src="https://github.com/user-attachments/assets/fc1edfbd-0369-415c-b5d4-c2d2827a852d" />

---

# 🎯 Desafio (DIY)

## Objetivo

Alterar o tipo da instância EC2 para uma instância de uso geral maior (**m4.large**).

### Situação Inicial

```text
t3.micro
```

### Situação Final

```text
m4.large
```

### Procedimento

1. Selecionar a instância EC2.
2. Parar a instância.
3. Acessar:

```text
Actions
 └── Instance Settings
      └── Change Instance Type
```

4. Alterar o tipo para:

```text
m4.large
```

5. Salvar a alteração.

<img width="1620" height="915" alt="Image" src="https://github.com/user-attachments/assets/6afc5792-adf9-45c1-aa43-179a0a7cfbff" />
<img width="1477" height="780" alt="Image" src="https://github.com/user-attachments/assets/a78646d8-42d3-4813-bc3f-5ee4c989c017" />

---

# 📂 Estrutura das Evidências

```text
evidencias/
│
├── 01-console-ec2.png
├── 02-tipos-instancia.png
├── 03-metadados.png
├── 04-ec2-instance-connect.png
├── 05-logs-aplicacao.png
├── 06-instancia-stopped.png
└── 07-alteracao-tipo-instancia.png
```

---

# 🛠️ Serviços Utilizados

- ☁️ Amazon EC2
- 🔐 EC2 Instance Connect
- ⚙️ AWS Systems Manager
- 📋 Instance Metadata Service (IMDS)
- 🌐 AWS Management Console

---

# 📚 Conhecimentos Adquiridos

Ao concluir este laboratório, foram praticados conceitos relacionados a:

- Computação em nuvem na AWS.
- Administração de instâncias EC2.
- Famílias e tipos de instâncias.
- Consulta de metadados.
- Conectividade segura em ambientes Linux.
- Gerenciamento do ciclo de vida de instâncias.
- Scale Up (Redimensionamento Vertical).

---

# ✅ Conclusão

Este laboratório proporcionou uma visão prática sobre os recursos de computação da AWS utilizando o Amazon EC2. Durante a atividade foram explorados conceitos importantes relacionados à conectividade, metadados, gerenciamento de instâncias e análise de diferentes famílias de máquinas virtuais. O desafio final demonstrou na prática o processo de redimensionamento vertical de recursos, alterando uma instância **t3.micro** para **m4.large**, reforçando conhecimentos fundamentais para administração e otimização de ambientes em nuvem AWS.

---

## 🏷️ Tags

`AWS` `AmazonEC2` `CloudComputing` `AWSQuest` `AWSSkillBuilder` `ComputeSolutions` `Infrastructure` `Cloud` `DevOps` `ScaleUp`
