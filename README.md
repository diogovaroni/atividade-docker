# Atividade Docker

## Execução em equipe

Alunos: Diogo Varoni, Daniel de Oliveira, Lucas Nathan, Mateus dos Anjos

Após ter realizado o tutorial de Docker, crie um conteiner com MySQL.
Esse conteiner deve ser criado desde o início, evite baixar conteineres prontos.
Sua equipe deve entregar o link para o git (ou similar) a ser baixado para uso.

Importante:

a. O conteiner tem de estar plenamente funcional (SO + MySql + Qualquer outro elemento necessário)

Alunos: Diogo Varoni, Daniel de Oliveira, Lucas Nathan, Mateus dos Anjos

### Senha servidor  MySQL: 123456

## Passo a passo da Atividade
### - Abra o PowerShell
### Comando para baixar uma imagem Docker do MySQL
docker pull mysql/mysql-server:latest

### Comando Criando o volume na máquina local, que se conecta ao Contâiner MySQL
docker volume create mysql-volume

### Comando para o Docker criar e rodar o servidor Mysql
docker run --name=servidor-mysql -p3306:3306 -v mysql-volume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql/mysql-server:latest

### Comando para verificar o Status do Processo
docker ps

### Comandos para entrar no Container
docker exec -it servidor-mysql bash

### Comandos para se conectar ao servidor MySQL de dentro do container
mysql -u root -p

### Comando para se conectar ao MySQL a partir da máquina local
update mysql.user set host='%' where user='root';

### Comando para que as alterações no usuário root tenham efeito
FLUSH PRIVILEGES;

### Teste do Servidor MySQL criado. Comando para criar uma tabela
CREATE DATABASE TESTE_DEVOPS;
