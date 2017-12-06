---

copyright:
  years: 2016,2017
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}} 애플리케이션 연결

{{site.data.keyword.cloud}} 애플리케이션을 서비스에 연결하려면 서비스가 프로비저닝될 때 작성된 서비스 신임 정보를 사용하십시오. 샘플 앱은 Node.js를 사용하여 제공된 신임 정보로 {{site.data.keyword.composeForRethinkDB_full}} 서비스에 연결하는 방법과 데이터베이스를 작성하고 데이터베이스에서 읽고 쓰는 방법을 보여줍니다.

## 'Hello World' 샘플 앱을 사용하여 연결

[compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) 샘플 앱은 Node.js를 사용하여 제공된 신임 정보로 {{site.data.keyword.composeForRethinkDB}} 서비스에 연결하는 방법을 보여줍니다. 이 애플리케이션은 데이터베이스를 작성하고 데이터베이스에서 읽고 씁니다.

샘플 앱을 다운로드하고 readme 파일의 지시사항에 따르십시오. 그런 다음 {{site.data.keyword.cloud_notm}}의 애플리케이션 세부사항 페이지에서 **앱 보기**를 클릭하여 *예제* 테이블의 컨텐츠를 표시하십시오.

## 사용 가능한 신임 정보

필드 이름 |설명
----------|-----------
`uri`|서비스에 연결할 때 사용할 URI입니다. 스키마(rethinkdb:), 관리 사용자 이름과 비밀번호, 서버의 호스트 이름, 연결할 포트 번호를 포함합니다. 
`uri_admin`|데이터베이스의 관리 인터페이스에 액세스하기 위해 브라우저에서 방문해야 하는 URI입니다. 액세스하려면 `uri` 필드의 관리 사용자 이름과 비밀번호가 필요합니다. 
`ca_certificate_base64`|애플리케이션이 적합한 서버에 연결되었는지 확인하는 데 사용되는 자체 서명된 인증서입니다. base64로 인코딩되어 있습니다. 샘플 애플리케이션에 표시된 대로 사용하기 전에 키를 디코딩해야 합니다. 
`deployment_id`|Compose에서 작성된 서비스의 내부 ID입니다. 
`db_type`|서비스에서 제공하는 데이터베이스의 유형입니다. 이 경우 `rethink`입니다. 
`name`|데이터베이스 배치 이름입니다. 
{: caption="표 1. Compose for RethinkDB 신임 정보" caption-side="top"}
