---
title: sys. sp_cdc_start_job (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cdc_start_job
- sp_cdc_start_job_TSQL
- sys.sp_cdc_start_job_TSQL
- sys.sp_cdc_start_job
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cdc_start_job
ms.assetid: cf443a67-7705-4799-9f39-0e3a6a8a0708
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a87fca28491075c9a75945b7a452c02b270d95b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891055"
---
# <a name="syssp_cdc_start_job-transact-sql"></a>sys.sp_cdc_start_job(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  현재 데이터베이스의 변경 데이터 캡처 정리 또는 캡처 작업을 시작합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sys.sp_cdc_start_job [ [ @job_type = ] 'job_type' ]  
```  
  
## <a name="arguments"></a>인수  
`[ [ @job_type = ] 'job_type' ]`추가할 작업 유형입니다. *job_type* 은 **nvarchar (20)** 이며 기본값은 **capture**입니다. 올바른 입력은 **캡처** 및 **정리**입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 None  
  
## <a name="remarks"></a>설명  
 sys.sp_cdc_start_job을 사용하면 관리자가 캡처 작업이나 정리 작업을 명시적으로 시작할 수 있습니다.  
  
## <a name="permissions"></a>사용 권한  
 db_owner 고정 데이터베이스 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-starting-a-capture-job"></a>A. 캡처 작업 시작  
 다음 예에서는 `AdventureWorks2012` 데이터베이스의 캡처 작업을 시작합니다. 기본 작업 유형이 **캡처**이기 때문에 *job_type* 값을 지정 하지 않아도 됩니다.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_start_job;  
GO  
```  
  
### <a name="b-starting-a-cleanup-job"></a>B. 정리 작업 시작  
 다음 예에서는 `AdventureWorks2012` 데이터베이스의 정리 작업을 시작합니다.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_start_job @job_type = N'cleanup';  
```  
  
## <a name="see-also"></a>참고 항목  
 [cdc_jobs &#40;Transact-sql&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)   
 [sp_cdc_stop_job &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-stop-job-transact-sql.md)  
  
  
