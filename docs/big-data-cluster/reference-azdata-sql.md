---
title: azdata sql 참조
titleSuffix: SQL Server big data clusters
description: azdata sql 명령에 대한 참조 문서입니다.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 06/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: bb7dd195d489be289cf434e8e4651ac17c6a6709
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242989"
---
# <a name="azdata-sql"></a>azdata sql

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

다음 문서에서는 `azdata` 도구의 `sql` 명령에 대한 참조를 제공합니다. 다른 `azdata` 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요.

## <a name="commands"></a>명령
| 명령 | 설명 |
| --- | --- |
[azdata sql shell](#azdata-sql-shell) | SQL DB CLI를 사용하여 사용자가 T-SQL을 통해 SQL Server를 조작할 수 있습니다.
[azdata sql query](#azdata-sql-query) | query 명령을 사용하여 T-SQL 쿼리를 실행할 수 있습니다.
## <a name="azdata-sql-shell"></a>azdata sql shell
SQL DB CLI를 사용하여 사용자가 T-SQL을 통해 SQL Server를 조작할 수 있습니다.
```bash
azdata sql shell 
```
### <a name="examples"></a>예제
대화형 환경을 시작하는 예제 명령줄입니다.
```bash
azdata sql shell
```
### <a name="global-arguments"></a>전역 인수
#### `--debug`
로깅의 자세한 정도를 늘려 모든 디버그 로그를 표시합니다.
#### `--help -h`
이 도움말 메시지를 표시하고 종료합니다.
#### `--output -o`
출력 형식입니다.  허용되는 값: json, jsonc, table, tsv  기본값: json
#### `--query -q`
JMESPath 쿼리 문자열입니다. 자세한 내용 및 예제는 [http://jmespath.org/](http://jmespath.org)를 참조하세요.
#### `--verbose`
로깅의 자세한 정도를 늘립니다. 전체 디버그 로그를 표시하려면 --debug를 사용합니다.
## <a name="azdata-sql-query"></a>azdata sql query
query 명령을 사용하여 T-SQL 쿼리를 실행할 수 있습니다.
```bash
azdata sql query --database -d 
                 -q
```
### <a name="examples"></a>예제
테이블 이름 목록을 선택합니다.  데이터베이스는 기본적으로 master로 설정됩니다.
```bash
azdata sql query "SELECT name FROM SYS.TABLES"
```
### <a name="required-parameters"></a>필수 매개 변수
#### `--database -d`
쿼리를 실행할 데이터베이스입니다.  기본값은 master입니다.
#### `-q`
실행할 T-SQL 쿼리입니다.
### <a name="global-arguments"></a>전역 인수
#### `--debug`
로깅의 자세한 정도를 늘려 모든 디버그 로그를 표시합니다.
#### `--help -h`
이 도움말 메시지를 표시하고 종료합니다.
#### `--output -o`
출력 형식입니다.  허용되는 값: json, jsonc, table, tsv  기본값: json
#### `--query -q`
JMESPath 쿼리 문자열입니다. 자세한 내용 및 예제는 [http://jmespath.org/](http://jmespath.org)를 참조하세요.
#### `--verbose`
로깅의 자세한 정도를 늘립니다. 전체 디버그 로그를 표시하려면 --debug를 사용합니다.

## <a name="next-steps"></a>다음 단계

다른 `azdata` 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요. `azdata` 도구를 설치하는 방법에 대한 자세한 내용은 [azdata를 설치하여 SQL Server 2019 빅 데이터 클러스터 관리](deploy-install-azdata.md)를 참조하세요.
