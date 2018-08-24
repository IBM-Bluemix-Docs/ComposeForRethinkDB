---
copyright:
  years: 2016,2018
lastupdated: "2018-06-14"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Arquitetura 
{: #architecture}

## Replicação

Um serviço {{site.data.keyword.composeForRethinkDB_full}} usa um cluster com três nós de dados. Quando você seleciona uma região na qual o serviço é implementado, os três nós são distribuídos pelas zonas de disponibilidade da região. Os clusters do RethinkDB consistem em um membro principal que coordenará as gravações.  Os membros adicionais podem se tornar principais no caso de uma falha do nó. Se um membro de dados se tornar inacessível, seu cluster continuará a operar normalmente.

### Configurando a replicação de seus dados

A replicação de seus dados nos nós **não** é um processo automático. Os dados são distribuídos pelo cluster com base na réplica e na contagem de shard de cada tabela. Você terá que configurar suas tabelas para distribuição pelos shards. Há três maneiras
de fazer isso.

1. Use a Interface da web RethinkDB. A URL para a interface da web integrada é a sequência de conexões do _Administrador_ fornecida na página _Visão geral_ do serviço. É possível configurar o sharding e a replicação para todas as suas tabelas lá.
2. Use o comando  ` reconfigurar `  ReQL. Mais sobre a sintaxe de `reconfigure` com o uso em diferentes linguagens pode ser localizado na [Referência de ReQL](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. É possível programar o aplicativo para configurar a replicação na criação de tabela usando o parâmetro _replicas_ opcional como `tableCreate`. Mais sobre a sintaxe de `tableCreate` com o uso em diferentes linguagens pode ser localizado na [Referência de ReQL](https://www.rethinkdb.com/api/javascript/table_create/).

## Criptografia de Disco

Todos os serviços do  {{site.data.keyword.composeForRethinkDB}}  têm criptografia em repouso. Seus dados residem em servidores que possuem criptografia em nível de volume ativada. 

Como o {{site.data.keyword.composeForRethinkDB}} é um serviço gerenciado, os operadores do {{site.data.keyword.cloud}} Compose podem ver os dados. Além da criptografia de disco, recomendamos criptografar informações pessoais antes de armazená-las no banco de dados ou usar extensões ou recursos para ativar a criptografia no próprio banco de dados. Embora esses métodos possam afetar a usabilidade ou o desempenho, é uma boa prática assegurar-se de que as informações pessoais sejam protegidas com criptografia.

## Auto-scaling

Os recursos são escalados automaticamente com base no uso total de armazenamento em disco dos bancos de dados RethinkDB. O uso de memória baseia-se em uma razão de armazenamento provisionado em uma proporção de 1:10. Esses recursos são empacotados como unidades.

O Auto-scaling foi projetado para responder às tendências de curto a médio prazo de seu banco de dados. A cada hora, seu serviço será verificado e, se ele estiver sendo executado com pouco espaço em disco, mais unidades serão alocadas para a implementação.

O Auto-scaling não reduz a capacidade de implementações em que o uso de disco/memória foi reduzido. Os recursos provisionados para seus bancos de dados permanecerão para suas necessidades futuras ou até você reduzir a capacidade de sua implementação manualmente.
{: .tip}
