---

Copyright:
  Years: 2017
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Conectando um aplicativo externo
{: #connecting-external-app}

Dependendo de qual driver você está usando, há várias maneiras de se conectar ao RethinkDB. O {{site.data.keyword.composeForRethinkDB_full}} usa uma sequência de conexões de formato de URI:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

Você localizará sua sequência de conexões na página *Visão geral* de seu serviço {{site.data.keyword.composeForPostgreSQL}}.

## Conectando-se ao SSL - Aplicativos

Atualmente e em nosso conhecimento, todos os quatro drivers RethinkDB oficialmente suportados (JavaScript, Python, Ruby e Java), bem como o driver Go (gorethink) suportam a conexão via SSL. Se estiver usando um driver diferente e tendo problemas com conexões SSL, você provavelmente desejará contatar os mantenedores do driver e informá-los o quanto deseja o suporte SSL para o RethinkDB.

Para assegurar que a conexão seja segura e evite ataques man-in-the-middle, será necessário capturar a Chave pública para a sua implementação. Quando você tiver isso, além das informações de conexão (host, porta, chave de aut.), dê uma olhada nos documentos do driver específico para a configuração de conexão adequada ou dê uma olhada neste artigo do Compose para [Exemplos de conexão do Python, Ruby, Node/Javascript e Go](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/). Se você estiver usando o Rethink 2.3 e desejar se conectar como um usuário diferente, consulte este artigo do Compose em *[Usando a autenticação do usuário do RethinkDB 2.3](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

Para suporte detalhado a aplicativos e drivers, verifique a documentação apropriada e as comunidades para a sua linguagem específica e o driver que o seu aplicativo está usando.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
