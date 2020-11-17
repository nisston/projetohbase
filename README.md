# Instalação e comandos básicos do Apache HBase

Disciplina: Banco de Dados

Prof. Dr. Carlos Eduardo Santos Pires

## Instalação do Apache HBase via Google Cloud

#### Guia de início rápido usando o shell do HBase

https://cloud.google.com/bigtable/docs/quickstart-hbase?hl=pt-br

#### Passo 1 - Acessando o ambiente da Google Cloud
-----
https://cloud.google.com/

Você pode logar com o domínio @copin.ufcg.edu.br para ter acesso ao serviço.

#### Passo 2 - Criando uma instância do Bigtable
-----
https://console.cloud.google.com/bigtable/create-instance?hl=pt-br

#### Passo 3 - Link para acesso ao console do Google Cloud
-----
https://console.cloud.google.com/projectselector2/home/dashboard?hl=pt-br

Não esquecer de deletar a instância após a utilização.

#### Comandos básicos do Apache HBase
-----

#### Passo 4 - Instalação e configuração do JDK para rodar o Apache HBase

``#Comandos de configuração do JDK para rodar o HBase``

``sudo apt-get update``

``sudo apt-get install openjdk-8-jdk-headless``

``export JAVA_HOME=$(update-alternatives --list java | tail -1 | sed -E 's/\/bin\/java//')``


``#Comandos para clonar um repositório exemplo de bigtable``

``git clone https://github.com/GoogleCloudPlatform/cloud-bigtable-examples.git``

``cd cloud-bigtable-examples/quickstart``


#### Passo 5 - Iniciando o HBase

``./quickstart.sh``

#### Criando uma tabela no HBase

``create 'cliente', 'cf1'``

#### Listando as tabelas existentes no HBase

``list``

#### Criando registros na tabela cliente com quatro colunas

``put 'cliente', 'r1', 'cf1:c1', 'maria'``

``put 'cliente', 'r1', 'cf1:c2', '222'``

``put 'cliente', 'r1', 'cf1:c3', 'http://www.empresa.com.br'``

``put 'cliente', 'r1', 'cf1:c4', '1000'``

#### Criando um novo registro na tabela cliente com quatro coluna 

``put 'cliente', 'r2', 'cf1:c1', 'pedro'``

``put 'cliente', 'r2', 'cf1:c2', '44444'``

``put 'cliente', 'r2', 'cf1:c3', 'http://www.empresaA.com.br'``

``put 'cliente', 'r2', 'cf1:c4', '200'``

#### Visualizando dados da tabela cliente

``scan 'cliente'``

#### Visualizando dados da tabela cliente com especificação de colunas

``scan 'cliente', {COLUMNS => ['cf1:c1','cf1:c4']}``

#### Outra maneira de visualizar dados da tabela

``get 'cliente', 'r1'``

#### Outra maneira de visualizar dados da tabela com a especificação de colunas

``get 'cliente', {COLUMNS => ['cf1:c1','cf1:c4']}``

#### Apagando registro

``delete 'cliente', 'r1', 'cf1:c4'``

#### Apagando a tabela cliente

``disable 'cliente'``

``drop 'cliente'``

## Link para mais comandos do HBase
https://learnhbase.net/2013/03/02/hbase-shell-commands/

## Link para vídeo no youtube

