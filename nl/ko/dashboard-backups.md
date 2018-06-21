---

copyright:
  years: 2017,2018
lastupdated: "2018-03-02"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 백업
{: #backups}

서비스 대시보드의 _관리_ 페이지에 있는 _백업_ 탭에서 백업을 작성하고 다운로드할 수 있습니다. 일별, 주별, 월별 및 요청 시 백업이 사용 가능합니다. 이들은 다음 스케줄에 따라 보존됩니다.

백업 유형|보존 스케줄
----------|-----------
일별|일별 백업은 7일 간 보존됨
주별|주별 백업은 4주 간 보존됨
월별|월별 백업은 3개월 간 보존됨
요청 시|1회의 요청 시 백업이 보존됩니다. 보존된 백업은 항상 최신 요청 시 백업입니다.
{: caption="표 1. 백업 보존 스케줄" caption-side="top"}

백업 스케줄 및 보존 정책은 고정되어 있습니다. 보존 스케줄이 허용하는 것보다 더 많은 백업을 보존해야 하는 경우에는 자신의 비즈니스 요구사항에 따라 백업을 다운로드하고 아카이브를 보존해야 합니다.

## 기존 백업 보기

데이터베이스의 일간 백업이 자동으로 스케줄됩니다. 기존 백업을 보려면 서비스 대시보드의 *관리* 페이지로 이동하십시오. 

  ![백업](./images/rethink-backups-show.png "서비스 대시보드의 백업 목록")

해당 행을 클릭하여 사용 가능한 백업에 대한 옵션을 펼치십시오.

  ![백업 옵션](./images/rethink-backups-options.png "백업에 대한 옵션") 

### API를 사용하여 기존 백업 보기

백업 목록은 `GET /2016-07/deployments/:id/backups` 엔드포인트에서 사용 가능합니다. 서비스 인스턴스 ID와 배치 ID가 모두 포함된 기반 엔드포인트가 서비스의 _개요_에 표시됩니다. 예를 들어, 다음과 같습니다. 
``` 
https://composebroker-dashboard-public.mybluemix.net/api/2016-07/instances/$INSTANCE_ID/deployments/$DEPLOYMENT_ID/backups
```  

## 요청 시 백업 작성

스케줄된 백업은 물론 수동으로 백업을 작성할 수도 있습니다. 수동 백업을 작성하려면 서비스 대시보드의 *관리* 페이지로 이동하여 *지금 백업*을 클릭하십시오.

### API를 사용하여 백업 작성

`POST /2016-07/deployments/:id/backups`를 통해 백업 엔드포인트에 POST 요청을 전송하여 수동 백업을 시작하십시오. 실행 중인 백업에 대한 정보와 레시피 ID를 즉시 리턴합니다. 백업 엔드포인트를 확인하여 백업이 완료되었는지 알아보고 백업을 사용하기 전에 해당 backup_id를 찾아야 합니다. `GET /2016-07/deployments/:id/backups/`를 사용하십시오.

## 백업 다운로드

백업을 다운로드하려면 서비스 대시보드의 *관리* 페이지로 이동하여 다운로드할 백업에 해당하는 행에서 *다운로드*를 클릭하십시오.

### API를 사용하여 백업 다운로드

서비스에 대한 _백업_ 페이지에서 복원하려는 백업을 찾아 backup_id를 복사하거나 `GET /2016-07/deployments/:id/backups`를 사용하여 Compose API를 통해 백업 및 해당 backup_id를 찾으십시오. 그런 다음, backup_id를 사용하여 특정 백업에 대한 정보와 다운로드 링크를 찾으십시오. `GET /2016-07/deployments/:id/backups/:backup_id`

## 백업 컨텐츠

RethinkDB 백업은 실행 중인 데이터베이스 클러스터의 RethinkDB 명령행 유틸리티에서 `dump` 명령을 사용하여 전체 배치를 백업합니다. 메타데이터만이 아니라 데이터베이스 및 테이블 컨텐츠도 저장합니다. `dump`는 일부 클러스터 리소스를 사용하지만 클라이언트를 잠그지 않고 활성 클러스터에서 실행될 수 있습니다. Compose는 `rethinkdb restore`에서 직접 사용할 수 있는 형식으로 RethinkDB 배치에 대한 백업을 제공합니다.

## 로컬 데이터베이스에 백업 사용

RethinkDB 백업을 다운로드할 수 있으므로 다운로드 배치의 로컬 인스턴스를 시작하여 실행할 수 있습니다.

1. [rethink](https://www.rethinkdb.com/docs/install/)를 설치하십시오.
2. [python 드라이버](https://www.rethinkdb.com/docs/install-drivers/python/)를 해당 경로에 설치하십시오.
3. 압축된 백업 파일을 다운로드하십시오. RethinkDB 도구에서 처리 방법을 알고 있으므로 백업 아카이브 파일의 압축을 풀 필요가 없습니다.
4. RethinkDB를 스핀업하려면 하나의 터미널 창에서 `rethinkdb` 명령을 실행하고 별도의 터미널 창에서 다운로드된 백업의 위치로 이동하여 `rethinkdb restore backup.tar.gz`를 실행하십시오.

브라우저 창을 열고 `locahost:8080`으로 이동하여 RethinkDB UI 및 데이터를 확인하십시오.

## 로컬 백업을 서비스로 가져오기

{{site.data.keyword.composeForRethinkDB}}에 복원하려는 백업 파일이 로컬에 있는 경우 `rethinkdb restore`를 사용하여 이를 수행할 수 있습니다.

1. [rethink](https://www.rethinkdb.com/docs/install/)를 설치하십시오.
2. [python 드라이버](https://www.rethinkdb.com/docs/install-drivers/python/)를 해당 경로에 설치하십시오.
3. 서비스의 *개요* 페이지에서 인증서를 다운로드하여 로컬에 compose.cert로 저장하십시오.
4. 다음 명령을 사용하여 백업에서 복원하십시오.

  ```
  rethinkdb restore -c <host>:<port> --tls-cert compose.cert -p backup.tar.gz
  ```

호스트 및 포트 값은 서비스의 *개요* 페이지에 있는 연결 문자열에서 찾을 수 있습니다. 명령의 `-p`는 _인증 신임 정보_에 대한 프롬프트를 표시합니다.

**참고:** 기존 배치에 복원 중인 경우 기존 테이블을 겹쳐쓰려면 `--force`를 사용해야 할 수도 있습니다.
