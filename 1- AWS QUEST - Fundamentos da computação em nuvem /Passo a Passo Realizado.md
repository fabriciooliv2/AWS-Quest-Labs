Etapa 1 - Acesso ao Serviço S3
Acesso ao Console AWS
Pesquisa pelo serviço Amazon S3
Abertura do painel do serviço

📷 Evidência:

evidencias/passo-03-acessar-s3.png

Etapa 2 - Seleção do Bucket
Localização do bucket disponibilizado para o laboratório
Acesso aos objetos armazenados

📷 Evidência:

evidencias/passo-04-selecionar-bucket.png

Etapa 3 - Revisão dos Arquivos do Site

Foram identificados os seguintes arquivos:

index.html
text.html
styles.css
main.js
target-file.csv

📷 Evidência:

evidencias/passo-05-revisar-arquivos.png

Etapa 4 - Renomeação da Página de Erro

O arquivo:

foi renomeado para:

Plain Text
1
error.html

📷 Evidência:

evidencias/passo-06-renomear-error-html.png

Etapa 5 - Configuração de Permissões

Validação das configurações de acesso público do bucket.

Configuração observada:

Plain Text
1
Block All Public Access = OFF

📷 Evidência:

evidencias/passo-08-validar-permissoes.png

Etapa 6 - Revisão da Política do Bucket

Política responsável por permitir acesso público aos objetos do bucket.

Permissão utilizada:

JSON
1
{
2
"Effect": "Allow",
3
"Principal": "*",
4
"Action": "s3:GetObject"
5
}
6
``*

📷 Evidência:

evidencias/passo-09-politica-bucket.png

Etapa 7 - Configuração da Hospedagem Estática

Acesso à seção:

Plain Text
1
*roperties > Static Website Hosting*

Configurações aplicadas:

Enable
Host a Static Website

📷 Evidência:

evidencias/passo-12-hospedagem-estatica.png

Etapa 8 - Definição dos Documentos

Documento principal:

Documento de erro:

Plain Text
1
error.html

📷 Evidência:

evidencias/passo-13-configurar-site.png

Etapa 9 - Salvamento das Configurações

Aplicação das alterações de hospedagem estática.

📷 Evidência:

evidencias/passo-14-salvar-configuracao.png

Etapa 10 - Validação do Endpoint

Após a configuração, foi gerado o endpoint público do site:

Plain Text
1
http://bucket-name.s3-website*region.amazonaws.com

📷 Evidência:

evidencias/passo-15-endpoint-site.png

Desafio (DIY)

Objetivo adicional proposto pelo laboratório:

Renomear:

Plain Text
1
index*html

para

Plain Text
1
waves.html*

e validar a alteração através do mecanismo disponibilizado pelo laboratório.

📷 Evidência:

evidencias/passo-16-validacao-final.png

Competências Desenvolvidas
Amazon S3
Static Website Hosting
Bucket Policies
Controle de Acesso
Hospedagem Web Estática
Gerenciamento de Objetos
Segurança em Buckets
Resultado

O bucket Amazon S3 foi configurado com sucesso para hospedagem estática de conteúdo web, permitindo acesso público aos arquivos através de um endpoint web dedicado.

✅ Site publicado

✅ Política aplicada

✅ Hospedagem estática habilitada

✅ Desafio final concluído
