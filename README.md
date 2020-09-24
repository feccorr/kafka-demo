# Producer e Consumer - Kafka

A ideia do sistema é fazer uma demo de uma aplicação Producer (input_01_covid), e Consumer (financeiro). Onde o sistema de input envia dados do número de casos de covid por data e região, salvando esses dados em um repositorio do mongoDB e enviando atraves de um topico no kafka, os dados a serem consumidos no sistema Financeiro.

## Instalando o Kafka

1) Realizar o download no site oficial do kafka : kafka.apache.org

2) Descompactar o conteudo em um diretorio. 
3) Iniciar o zookeeper :

```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```
4) Iniciar o servidor do kafka :

```bash
bin/kafka-server-start.sh config/server.properties
```

## Sistema - input_01_covid

Modulo usado para enviar os dados atraves de um topico no kafka, a serem consumidos pelo modulo financeiro. Possui uma api com método post para salvar os dados no mongodb, a interface do swagger pode ser acessada na seguinte URL :

```bash
http://localhost:8080/swagger-ui.html
```

## Sistema - Financeiro

Modulo usado para receber os dados de covid por regiao e data atraves do topico 'saude-covid-input', o sistema possui um metodo post para salvar no mongodb os dados recebidos atraves do kafka e um método get para dividir uma verba baseado nos casos por regiao em uma data especifica , a interface do swagger pode ser acessada na seguinte URL :

```bash
http://localhost:8081/swagger-ui.html
```
