---
title: dbo.sysjobschedules (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysjobschedules
- dbo.sysjobschedules
- dbo.sysjobschedules_TSQL
- sysjobschedules_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysjobschedules system table
ms.assetid: ccdafec7-2a9b-4356-bffb-1caa3a12db59
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1404af2beddd9cd3c5e5c65420cbe248396dd09c
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890479"
---
# <a name="dbosysjobschedules-transact-sql"></a>dbo.sysjobschedules(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트가 실행할 작업에 관한 일정 정보를 포함합니다. 이 테이블은 **msdb** 데이터베이스에 저장 됩니다.  
  
> **참고:** **Sysjobschedules** 테이블은 20 분 마다 새로 고쳐지고 **sp_help_jobschedule** 저장 프로시저에서 반환 하는 값에 영향을 줄 수 있습니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**schedule_id**|**int**|일정의 ID입니다.|  
|**job_id**|**uniqueidentifier**|작업의 ID입니다.|  
|**next_run_date**|**int**|작업을 실행하도록 예약된 다음 날짜입니다. 날짜 형식은 YYYYMMDD입니다.|  
|**next_run_time**|**int**|작업을 실행하도록 예약된 시간입니다. 시간 형식은 HHMMSS이며 24시간제를 사용합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;dbo.sys일정](../../relational-databases/system-tables/dbo-sysschedules-transact-sql.md)  
  
  
