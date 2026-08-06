# Lab 01 - Fundamentos da Computação em Nuvem

## 📖 Descrição

Neste laboratório foi realizada a migração de um site para hospedagem estática utilizando o Amazon S3.

O objetivo foi compreender os conceitos fundamentais de armazenamento em nuvem, controle de acesso e publicação de conteúdo web utilizando serviços gerenciados da AWS.

---

## 🎯 Objetivos do Laboratório

- Habilitar hospedagem estática em um bucket Amazon S3.
- Revisar as permissões do bucket.
- Analisar a política de acesso.
- Configurar documentos de índice e erro.
- Validar o endpoint público do site.
- Concluir o desafio adicional proposto.

---

## 🏗️ Arquitetura Simplificada

```text
Usuário
   │
   ▼
Amazon S3 Website Endpoint
   │
   ▼
Bucket S3
├── index.html
├── error.html
├── styles.css
├── main.js
└── target-file.csv
```

# 🚀 Desenvolvimento da Atividade

## Etapa 1 - Acesso ao Serviço S3

Acesso ao Console AWS

Pesquisa pelo serviço Amazon S3

Abertura do painel do serviço

<img width="1396" height="677" alt="Image" src="https://github.com/user-attachments/assets/a837ef7f-fbbd-4aeb-9b95-54c788281f34" />
________________________________________________________________________________________________________________________________________________________


## Etapa 2 - Seleção do Bucket

Localização do bucket disponibilizado para o laboratório

Acesso aos objetos armazenados

<img width="1397" height="680" alt="Image" src="https://github.com/user-attachments/assets/aa72fa58-59a3-4371-911d-ac92a1305aa4" />
________________________________________________________________________________________________________________________________________________________

## Etapa 3 - Revisão dos Arquivos do Site

Foram identificados os seguintes arquivos:

index.html

text.html

styles.css

main.js

target-file.csv

<img width="1399" height="683" alt="Image" src="https://github.com/user-attachments/assets/e4bc082a-766c-4312-b24d-d9be0c1d4c07" />
________________________________________________________________________________________________________________________________________________________

## Etapa 4 - Renomeação da Página de Erro

O arquivo foi renomeado para "error.html"

<img width="1398" height="677" alt="Image" src="https://github.com/user-attachments/assets/eb6e5aa5-b2f4-4451-9722-313e46842f1e" />
________________________________________________________________________________________________________________________________________________________

## Etapa 5 - Configuração de Permissões

Validação das configurações de acesso público do bucket.

Configuração observada:

"Block All Public Access = OFF"

<img width="1398" height="675" alt="Image" src="https://github.com/user-attachments/assets/0e1c137e-c0fa-4f79-9c33-491dece8a168" />
________________________________________________________________________________________________________________________________________________________

## Etapa 6 - Revisão da Política do Bucket

Política responsável por permitir acesso público aos objetos do bucket.

Permissão utilizada: JSON

{

  "Effect": "Allow",
  
  "Principal": "*",
  
  "Action": "s3:GetObject"
  
}

<img width="1398" height="674" alt="Image" src="https://github.com/user-attachments/assets/f9aec9bf-f203-4ba0-a8d9-db5ab324a917" />
________________________________________________________________________________________________________________________________________________________

## Etapa 7 - Configuração da Hospedagem Estática

Acesso à seção: *Properties > Static Website Hosting*

Configurações aplicadas:

"Enable"

"Host a Static Website"

<img width="1393" height="671" alt="Image" src="https://github.com/user-attachments/assets/6989c5da-9673-4c34-9e7f-7d6b7103dca5" />
________________________________________________________________________________________________________________________________________________________

## Etapa 8 - Definição dos Documentos

Documento principal: "index.html"

Documento de erro: "error.html"

<img width="1393" height="676" alt="Image" src="https://github.com/user-attachments/assets/ab021041-2f0f-47ec-ba09-6d109f52b53e" />
________________________________________________________________________________________________________________________________________________________

## Etapa 9 - Salvamento das Configurações

Aplicação das alterações de hospedagem estática.

<img width="1399" height="674" alt="Image" src="https://github.com/user-attachments/assets/4ce57f7b-a7f6-4399-8508-0e9306a7710e" />
________________________________________________________________________________________________________________________________________________________

## Etapa 10 - Validação do Endpoint

Após a configuração, foi gerado o endpoint público do site:

http://bucket-name.s3-website*region.amazonaws.com

# Desafio (DIY)

Objetivo adicional proposto pelo laboratório:

Renomear o arquivo "index.html" para "waves.html" 
e validar a alteração através do mecanismo disponibilizado pelo laboratório.

<img width="1629" height="917" alt="Image" src="https://github.com/user-attachments/assets/9405db72-e0a0-4d6e-ac2a-a33ae753c68e" />
________________________________________________________________________________________________________________________________________________________

# Competências Desenvolvidas

Amazon S3

Static Website Hosting

Bucket Policies

Controle de Acesso

Hospedagem Web Estática

Gerenciamento de Objetos

Segurança em Buckets

# Atribuições adquiridas

<img width="1490" height="784" alt="Image" src="https://github.com/user-attachments/assets/d2caa2c4-80b8-4d1b-bce4-8b867239e9c2" />

# Resultado

O bucket Amazon S3 foi configurado com sucesso para hospedagem estática de conteúdo web, permitindo acesso público aos arquivos através de um endpoint web dedicado.

✅ Site publicado

✅ Política aplicada

✅ Hospedagem estática habilitada

✅ Desafio final concluído


