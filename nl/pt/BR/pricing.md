---

copyright:
  years: 2016,2018
lastupdated: "2018-01-03"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Preços
{: #pricing}

## Configuração base

Um serviço {{site.data.keyword.composeForRethinkDB_full}} começa como um cluster de três nós de dados. Cada nó de dados tem 1 GB de armazenamento e 102 MB de memória, que é igual a 1 unidade de recursos. O serviço _inclui_ replicação e alta disponibilidade, portanto, cada unidade e o preço por unidade _incluem_ o custo dos recursos em todos os nós.

A configuração base também inclui um portal haproxy para fornecer suporte SSL para o cluster. O portal haproxy tem 64 MB de memória.

A configuração de serviço de base tem um preço definido. Consulte o ladrilho de catálogo no {{site.data.keyword.cloud_notm}} para precificação base em sua moeda local. Por exemplo, o preço base em dólares americanos é $18/mês.

## Aumentando recursos

Se você precisar de armazenamento ou memória adicional para o seu serviço, será possível aumentar os recursos alocados em uma razão 10:1 de armazenamento em disco para unidade de memória. Aumentar o disco alocado para a implementação também aumentará a RAM alocada. Uma unidade do {{site.data.keyword.composeForRethinkDB}} consiste em 1 GB de armazenamento e 102 MB de memória e cada unidade e o preço por unidade _incluem_ o custo para aumentar os recursos em todos os três nós de dados.

## Calculando o custo de sua implementação
{: #tiered-pricing}

Cada unidade adicional (1 GB de armazenamento/102 MB de memória) tem um preço por unidade que é listado em sua moeda local no quadro de catálogo do {{site.data.keyword.cloud_notm}} para o serviço. Em dólares americanos cada unidade adicional custa $18. Conforme o tamanho _total_ de todos os serviços do {{site.data.keyword.composeForRethinkDB}} aumenta, o preço por unidade diminui, conforme mostrado na tabela de precificação em camadas.

Número de unidades|Preço por unidade
----------|-----------
1 - 9 unidades|preço base por unidade -- US$18,00/Unidade
10 - 24 unidades|10% redução -- US$16,20/Unidade
25 - 49 unidades|20% redução -- US$14,40/Unidade
50 - 99 unidades|30% redução -- US$12,60/Unidade
100 - 499 unidades|40% redução -- US$10,80/Unidade
500 - 999 unidades|50% redução -- US$9,00/Unidade
1.000 - 4.999 unidades|60% redução -- US$7,20/Unidade
+ de 5.000 unidades|70% redução -- US$5,40/Unidade
{: caption="Tabela 1. Precificação em camadas do {{site.data.keyword.composeForRethinkDB}}" caption-side="top"}
