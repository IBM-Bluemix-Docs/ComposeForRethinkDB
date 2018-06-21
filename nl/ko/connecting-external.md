---

copyright:
  years: 2017,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 외부 애플리케이션 연결
{: #connecting-external-app}

사용 중인 드라이버에 따라 RethinkDB에 연결하는 여러 가지 방법이 있습니다. {{site.data.keyword.composeForRethinkDB_full}}에서는 URI 형식 연결 문자열을 사용합니다.

```
rethinkdb://[username]:[password]@[host]:[port]/
```

{{site.data.keyword.composeForPostgreSQL}} 서비스의 *개요* 페이지에서 연결 문자열을 찾을 수 있습니다.

## SSL을 사용하여 연결 - 애플리케이션

현재 알려진 바로는 Go 드라이버(gorethink)와 공식적으로 지원되는 4개의 모든 RethinkDB 드라이버(JavaScript, Python, Ruby 및 Java)가 SSL을 통한 연결을 지원합니다. 다른 드라이버를 사용 중이고 SSL 연결에 문제가 있는 경우 드라이버 유지보수 담당자에게 문의하여 RethinkDB에 대한 SSL 지원이 얼마나 필요한지 알리십시오.

연결이 안전하고 메시지 가로채기(man-in-the-middle) 공격을 방지하는지 확인하려면 배치에 대한 공개 키를 가져와야 합니다. 해당 공개 키와 연결 정보(호스트, 포트, 인증 키)가 있으면 적절한 연결 설정을 위한 특정 드라이버 문서를 살펴보거나 [Python, Ruby, Node/Javascript 및 Go 연결 예제](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/)의 경우 이 Compose 문서를 살펴보십시오. Rethink 2.3을 사용 중이고 다른 사용자로 연결하려면 *[RethinkDB 2.3의 사용자 인증 사용](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*에서 이 Compose 문서를 참조하십시오.

자세한 애플리케이션 및 드라이버 지원은 특정 언어와 애플리케이션에서 사용 중인 드라이버에 해당하는 문서와 커뮤니티를 확인하십시오.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
