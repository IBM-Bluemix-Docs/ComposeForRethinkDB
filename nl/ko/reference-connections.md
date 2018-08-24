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

# 연결 구성
{: #connection-configuration}

{{site.data.keyword.composeForRethinkDB_full}} 데이터베이스 연결은 RethinkDB 프록시 포털에서 관리합니다.

## 전송 중 암호화

{{site.data.keyword.composeForRethinkDB}} 프록시 포털에서는 TLS/SSL을 사용하고 TLS 버전 1.2를 지원합니다. 서비스의 인증서는 자체 서명된 인증서입니다. 서비스용 인증서의 로컬 사본을 저장하고 보안 연결을 위해 해당 위치를 애플리케이션 드라이버에 제공해야 할 수도 있습니다.

## 연결 한계

데이터베이스 연결에서 포털당 연결 한계는 2000개입니다. 연결 한계를 초과하면 서비스가 응답하지 않습니다. 드라이버의 연결 풀링 기능을 통해 애플리케이션에서의 연결을 관리할 수 있습니다.

## 프록시 제한시간

프록시 포털에서 서버와 클라이언트 간 연결의 라이프사이클을 관리합니다. 여기에서는 드라이버 작성자 및 {{site.data.keyword.composeForRethinkDB}} 데이터베이스 연결의 하위 레벨 활동에 관심이 있는 사용자용 참조서로 자세히 설명합니다.

설정 |값 | 적용
----------|-----------|-----------
client | 5m | 클라이언트에서 데이터를 수신확인하거나 전송할 것으로 예상되는 경우.
connect | 4s | 프록시와 서버 간에 연결 중인 경우.
server | 5m | 서버에서 데이터를 수신확인하거나 전송할 것으로 예상되는 경우.
tunnel | 1일 | 클라이언트와 서버 간에 양방향 연결이 설정되고 연결이 두 방향 모두에서 비활성 상태로 유지되는 경우.
client-fin | 1h | 한 방향이 이미 종료되어 있는 동안 클라이언트에서 데이터를 수신확인하거나 전송할 것으로 예상되는 경우.
check | 5s | 프록시와 서버를 서로 연결 중일 때 2차 제한시간 확인으로 사용하는 경우.
{: caption="표 1. RethinkDB 프록시 제한시간" caption-side="top"}
