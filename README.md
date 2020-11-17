# Intalação, Configuração e Execução do Apache HBase
Projeto desenvolvido na disciplina de Banco de Dados.

-----

## Apache HBase via Google Cloud

#### Acessando o ambiente da Google Cloud
-----

https://cloud.google.com/bigtable/docs/quickstart-hbase?hl=pt-br

#### Link para acesso ao cloud do google
-----

https://cloud.google.com/bigtable/docs/quickstart-hbase?hl=pt-br

#### Link para acesso ao console do cloud do google
-----

https://console.cloud.google.com/projectselector2/home/dashboard?hl=pt-br

#### Link para comandos básicos no HBase
-----

https://learnhbase.net/2013/03/02/hbase-shell-commands/


Navegue até a pasta desejada e realize o download através do comando

``wget https://github.com/bitnami/bitnami-docker-cassandra/blob/master/docker-compose-cluster.yml -O docker-compose.yml``

-----

##Comandos de configuração
-----

#### Instalação do JDK para rodar o HBase

``#Comandos de configuração do JDK para rodar o HBase
sudo apt-get update
sudo apt-get install openjdk-8-jdk-headless
export JAVA_HOME=$(update-alternatives --list java | tail -1 | sed -E 's/\/bin\/java//')``

``#Clonando um repositório exemplo de bigtable
git clone https://github.com/GoogleCloudPlatform/cloud-bigtable-examples.git
cd cloud-bigtable-examples/quickstart``


``#Iniciando o HBase
./quickstart.sh``


``#Criando tabela
create 'cliente', 'cf1'``

``#Listando as tabelas existentes
list``

``#Criando registros na tabela
put 'cliente', 'r1', 'cf1:c1', 'maria'
put 'cliente', 'r1', 'cf1:c2', '222'
put 'cliente', 'r1', 'cf1:c3', 'http://www.empresa.com.br'
put 'cliente', 'r1', 'cf1:c4', '1000'``

``#Criando um novo registro da mesma coluna 
put 'cliente', 'r2', 'cf1:c1', 'pedro'
put 'cliente', 'r2', 'cf1:c2', '44444'
put 'cliente', 'r2', 'cf1:c3', 'http://www.empresaA.com.br'
put 'cliente', 'r2', 'cf1:c4', '200'``

#Recuperando dados das tabelas
``scan 'cliente'``

#Recuperando dados de mais de uma coluna
``scan 'cliente', {COLUMNS => ['cf1:c1','cf1:c4']}``

#Outra maneira de recupara dados
``get 'cliente', 'r1'``

``get 'cliente', {COLUMNS => ['cf1:c1','cf1:c4']}``


#### Deletando registro

``#Deletando um registro
delete 'cliente', 'r1', 'cf1:c4'``


#Apagando a tabela cliente
``disable 'cliente'
drop 'cliente'``


create 'fornecedor', 'cf2'

put 'fornecedor', 'r1', 'cf1:c1', 'empresa A'
put 'fornecedor', 'r2', 'cf1:c2', '8888'
put 'fornecedor', 'r3', 'cf2:c3', 'http://www.fornecedor.com.br'
put 'fornecedor', 'r4', 'cf2:c4', '10'

