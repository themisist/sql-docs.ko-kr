---
title: Cacheobjects sys.sys(Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.syscacheobjects_TSQL
- sys.syscacheobjects
- syscacheobjects
- syscacheobjects_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syscacheobjects system table
- sys.syscacheobjects compatibility view
ms.assetid: 9b14f37c-b7f5-4f71-b070-cce89a83f69e
author: rothja
ms.author: jroth
ms.openlocfilehash: a4d065ba57ab90e1bb035a6ef92100d351d93603
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899946"
---
# <a name="syssyscacheobjects-transact-sql"></a>sys.syscacheobjects(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  캐시 사용 방법에 대한 정보를 포함합니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**bucketid**|**int**|버킷 ID입니다. 값은 0에서 디렉터리 크기 - 1까지의 범위를 나타냅니다. 디렉터리 크기는 해시 테이블의 크기입니다.|  
|**cacheobjtype**|**nvarchar(17)**|캐시에 있는 개체의 유형입니다.<br /><br /> 컴파일된 계획<br /><br /> 실행 계획<br /><br /> 구문 분석 트리<br /><br /> 커서<br /><br /> 확장 저장 프로시저|  
|**objtype**|**nvarchar(8)**|개체의 유형입니다.<br /><br /> 저장 프로시저<br /><br /> 준비된 문<br /><br /> 임시 쿼리 ( [!INCLUDE[tsql](../../includes/tsql-md.md)] 원격 프로시저 호출 대신 **sqlcmd** 또는 **osql** 유틸리티에서 언어 이벤트로 제출 됨)<br /><br /> ReplProc(복제 프로시저)<br /><br /> 트리거<br /><br /> 보기<br /><br /> 기본값<br /><br /> 사용자 테이블<br /><br /> 시스템 테이블<br /><br /> 확인<br /><br /> 규칙|  
|**objid**|**int**|캐시에서 개체를 찾는 데 사용되는 기본 키 중 하나입니다. 데이터베이스 개체 (프로시저, 뷰, 트리거 등)의 경우 **sysobjects** 에 저장 된 개체 ID입니다. 임시 또는 준비 된 SQL과 같은 캐시 개체의 경우 **objid** 는 내부적으로 생성 된 값입니다.|  
|**dbid**|**smallint**|캐시 개체가 컴파일된 데이터베이스의 ID입니다.|  
|**dbidexec**|**smallint**|쿼리를 실행할 데이터베이스 ID입니다.<br /><br /> 대부분의 개체에 대해, **dbidexec** 는 **dbid**와 동일한 값을 갖습니다.<br /><br /> 시스템 보기의 경우에는 쿼리가 실행 되는 데이터베이스 ID가 **dbidexec** 입니다.<br /><br /> 임시 쿼리의 경우 **dbidexec** 는 0입니다. 즉, **dbidexec** 에는 **dbid**와 동일한 값이 있습니다.|  
|**uid**|**smallint**|임시 쿼리 계획 및 준비된 계획에서 계획을 만든 이를 나타냅니다.<br /><br /> -2는 전송된 일괄 처리가 암시적 이름 확인에 의존하지 않으며 여러 사용자들 간에 공유될 수 있음을 의미합니다. 이는 선호되는 방법입니다. 기타 값은 모두 데이터베이스에 쿼리를 전송하는 사용자의 사용자 ID를 나타냅니다.<br /><br /> 사용자 및 역할 수가 32,767을 초과하는 경우 오버플로되거나 NULL을 반환합니다.|  
|**refcounts**|**int**|이 캐시 개체를 참조하는 다른 캐시 개체의 수입니다. 1이 기본입니다.|  
|**usecounts**|**int**|이 캐시 개체가 시작된 이래로 사용된 횟수입니다.|  
|**pagesused**|**int**|캐시 개체에서 사용한 페이지 수입니다.|  
|**setopts**|**int**|컴파일된 계획에 영향을 미치는 SET 옵션 설정입니다. 이 설정은 캐시 키의 일부입니다. 이 열 값이 변경되었다면 사용자가 SET 옵션을 수정한 것입니다. 옵션은 다음과 같습니다.<br /><br /> **ANSI_PADDING**<br /><br /> **FORCEPLAN**<br /><br /> **CONCAT_NULL_YIELDS_NULL**<br /><br /> **ANSI_WARNINGS**<br /><br /> **ANSI_NULLS**<br /><br /> **QUOTED_IDENTIFIER**<br /><br /> **ANSI_NULL_DFLT_ON**<br /><br /> **ANSI_NULL_DFLT_OFF**|  
|**langid**|**smallint**|언어 ID입니다. 캐시 개체를 만든 연결의 언어 ID입니다.|  
|**dateformat**|**smallint**|캐시 개체를 만든 연결의 날짜 형식입니다.|  
|**status**|**int**|캐시 개체가 커서 계획인지 여부를 나타냅니다. 현재는 가장 중요하지 않은 비트만 사용됩니다.|  
|**lasttime**|**bigint**|이전 버전과의 호환성을 위해서만 지원됩니다. 항상 0을 반환합니다.|  
|**maxexectime**|**bigint**|이전 버전과의 호환성을 위해서만 지원됩니다. 항상 0을 반환합니다.|  
|**avgexectime**|**bigint**|이전 버전과의 호환성을 위해서만 지원됩니다. 항상 0을 반환합니다.|  
|**lastreads**|**bigint**|이전 버전과의 호환성을 위해서만 지원됩니다. 항상 0을 반환합니다.|  
|**lastwrites**|**bigint**|이전 버전과의 호환성을 위해서만 지원됩니다. 항상 0을 반환합니다.|  
|**sqlbytes**|**int**|전송된 일괄 처리 또는 프로시저 정의의 길이(바이트)입니다.|  
|**sql**|**nvarchar(3900)**|전송된 일괄 처리의 처음 3,900자 또는 모듈 정의입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [호환성 뷰&#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  

