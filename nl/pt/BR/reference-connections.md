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

# Configuração da Conexão
{: #connection-configuration}

As conexões com o banco de dados do {{site.data.keyword.composeForRethinkDB_full}} são gerenciadas por um portal Proxy do RethinkDB.

## Criptografia em Trânsito

O portal Proxy do {{site.data.keyword.composeForRethinkDB}} tem o TLS/SSL ativado e suporta o TLS versão 1.2. O certificado do serviço é um certificado auto-assinado. Talvez você tenha que salvar uma cópia local do certificado de seu serviço e fornecer seu local para o driver de seus aplicativos para fazer uma conexão segura.

## Limites de Conexão

As conexões com o banco de dados têm um limite de 2000 conexões por portal. Exceder o limite de conexão tornará seu serviço não responsivo. É possível gerenciar conexões de seu aplicativo por meio do recurso de definição do conjunto de conexões do driver.

## Tempos limite de proxy

O portal Proxy gerencia o ciclo de vida de conexões entre o servidor e o cliente. Nós as detalhamos aqui como uma referência para gravadores de driver e outros que têm interesse na atividade de baixo nível de conexões com o banco de dados do {{site.data.keyword.composeForRethinkDB}}.

Configurando | Value | Aplica
----------|-----------|-----------
cliente | 5m | Quando se espera que o cliente reconheça ou envie dados.
conectar | 4s | Quando uma conexão está sendo feita entre o proxy e o servidor.
server | 5m | Quando se espera que o servidor reconheça ou envie dados.
túnel | 1 dia | Quando uma conexão bidirecional é estabelecida entre um cliente e um servidor e a conexão permanece inativa em ambas as direções.
cliente-fin | 1h | Quando se espera que o cliente reconheça ou envie dados enquanto uma direção já está encerrada.
check | 5s | Como uma verificação de tempo limite secundário quando uma conexão está sendo feita entre o proxy e o servidor.
{: caption="Tabela 1. Tempos limite de proxy do RethinkDB" caption-side="top"}
