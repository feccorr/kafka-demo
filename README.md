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
