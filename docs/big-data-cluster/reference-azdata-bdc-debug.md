---
title: azdata bdc debug 참조
titleSuffix: SQL Server big data clusters
description: azdata bdc debug 명령에 대한 참조 문서입니다.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 11/04/2019
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: cccdc543a572df19849afec16d0a2a71413ed19e
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "74820889"
---
# <a name="azdata-bdc-debug"></a>azdata bdc debug

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]  

다음 문서에서는 `azdata` 도구의 `bdc debug` 명령에 대한 참조를 제공합니다. 다른 `azdata` 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요.

## <a name="commands"></a>명령
|     |     |
| --- | --- |
[azdata bdc debug copy-logs](#azdata-bdc-debug-copy-logs) | 로그를 복사합니다.
[azdata bdc debug dump](#azdata-bdc-debug-dump) | 로깅 덤프를 트리거합니다.
## <a name="azdata-bdc-debug-copy-logs"></a>azdata bdc debug copy-logs
빅 데이터 클러스터에서 디버그 로그를 복사합니다. 시스템에 Kubernetes 구성이 있어야 합니다.
```bash
azdata bdc debug copy-logs --namespace -n 
                           [--container -c]  
                           [--target-folder -d]  
                           [--pod -p]  
                           [--timeout -t]  
                           [--skip-compress -sc]  
                           [--exclude-dumps -ed]
```
### <a name="required-parameters"></a>필수 매개 변수
#### `--namespace -n`
Kubernetes 네임스페이스에 사용되는 빅 데이터 클러스터 이름입니다.
### <a name="optional-parameters"></a>선택적 매개 변수
#### `--container -c`
유사한 이름을 가진 컨테이너의 로그를 복사합니다. 선택 사항이며, 기본적으로 모든 컨테이너의 로그를 복사합니다. 여러 번 지정할 수 없습니다. 여러 번 지정하면 마지막 항목이 사용됩니다.
#### `--target-folder -d`
로그를 복사할 대상 폴더 경로입니다. 선택 사항이며, 기본적으로 로컬 폴더에 결과를 만듭니다.  여러 번 지정할 수 없습니다. 여러 번 지정하면 마지막 항목이 사용됩니다.
#### `--pod -p`
유사한 이름을 가진 Pod의 로그를 복사합니다. 선택 사항이며, 기본적으로 모든 Pod의 로그를 복사합니다. 여러 번 지정할 수 없습니다. 여러 번 지정하면 마지막 항목이 사용됩니다.
#### `--timeout -t`
명령이 완료될 때까지 대기할 시간(초)입니다. 기본값은 0으로, 무제한입니다.
#### `--skip-compress -sc`
결과 폴더 압축을 건너뛸지 여부를 지정합니다. 기본값은 False입니다. 이 값은 결과 폴더를 압축합니다.
#### `--exclude-dumps -ed`
결과 폴더에서 덤프를 제외할지 여부를 지정합니다. 기본값은 False입니다. 이 값은 덤프를 포함합니다.
### <a name="global-arguments"></a>전역 인수
#### `--debug`
로깅의 자세한 정도를 늘려 모든 디버그 로그를 표시합니다.
#### `--help -h`
이 도움말 메시지를 표시하고 종료합니다.
#### `--output -o`
출력 형식입니다.  허용되는 값: json, jsonc, table, tsv  기본값: json
#### `--query -q`
JMESPath 쿼리 문자열입니다. 자세한 내용 및 예제는 [http://jmespath.org/](http://jmespath.org/)를 참조하세요.
#### `--verbose`
로깅의 자세한 정도를 늘립니다. 전체 디버그 로그를 표시하려면 --debug를 사용합니다.
## <a name="azdata-bdc-debug-dump"></a>azdata bdc debug dump
로깅 덤프를 트리거하고 컨테이너에서 복사합니다. 시스템에 Kubernetes 구성이 있어야 합니다.
```bash
azdata bdc debug dump --namespace -n 
                      --container -c  
                      [--target-folder -d]
```
### <a name="required-parameters"></a>필수 매개 변수
#### `--namespace -n`
Kubernetes 네임스페이스에 사용되는 빅 데이터 클러스터 이름입니다.
#### `--container -c`
유사한 이름을 가진 컨테이너의 로그를 복사합니다. 선택 사항이며, 기본적으로 모든 컨테이너의 로그를 복사합니다. 여러 번 지정할 수 없습니다. 여러 번 지정하면 마지막 항목이 사용됩니다.
### <a name="optional-parameters"></a>선택적 매개 변수
#### `--target-folder -d`
로그를 복사할 대상 폴더 경로입니다. 선택 사항이며, 기본적으로 로컬 폴더에 결과를 만듭니다.  여러 번 지정할 수 없습니다. 여러 번 지정하면 마지막 항목이 사용됩니다(`./output/dump`).
### <a name="global-arguments"></a>전역 인수
#### `--debug`
로깅의 자세한 정도를 늘려 모든 디버그 로그를 표시합니다.
#### `--help -h`
이 도움말 메시지를 표시하고 종료합니다.
#### `--output -o`
출력 형식입니다.  허용되는 값: json, jsonc, table, tsv  기본값: json
#### `--query -q`
JMESPath 쿼리 문자열입니다. 자세한 내용 및 예제는 [http://jmespath.org/](http://jmespath.org/)를 참조하세요.
#### `--verbose`
로깅의 자세한 정도를 늘립니다. 전체 디버그 로그를 표시하려면 --debug를 사용합니다.

## <a name="next-steps"></a>다음 단계

다른 `azdata` 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요. `azdata` 도구를 설치하는 방법에 대한 자세한 내용은 [azdata를 설치하여 SQL Server 2019 빅 데이터 클러스터 관리](deploy-install-azdata.md)를 참조하세요.
