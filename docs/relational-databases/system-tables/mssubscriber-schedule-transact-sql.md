---
title: MSsubscriber_schedule (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSsubscriber_schedule
- MSsubscriber_schedule_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSsubscriber_schedule system table
ms.assetid: ff428306-0ef4-49a3-b536-07ccdf6e2196
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c5b4a3ac4c00dcb90d62961554d7bc4d12911f6f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889375"
---
# <a name="mssubscriber_schedule-transact-sql"></a>MSsubscriber_schedule(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSsubscriber_schedule** 테이블에는 각 게시자/구독자 쌍에 대 한 기본 병합 및 트랜잭션 동기화 일정이 포함 되어 있습니다. 이 테이블은 배포 데이터베이스에 저장됩니다.  
  
> [!NOTE]
>  이 시스템 테이블은 더 이상 사용 되지 않으며 이전 버전의를 지원 하기 위해 유지 관리 되 고 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 있습니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**발행자**|**sysname**|게시자의 이름입니다.|  
|**구독자**|**sysname**|구독자 이름입니다.|  
|**agent_type**|**smallint**|에이전트의 유형입니다.<br /><br /> 0 = 배포 에이전트<br /><br /> 1 = 병합 에이전트|  
|**frequency_type**|**int**|배포 에이전트의 일정을 지정하는 빈도입니다.<br /><br /> **1** = 한 번<br /><br /> **2** = 요청 시<br /><br /> **4** = 매일<br /><br /> **8** = 매주<br /><br /> **16** = 매월<br /><br /> **32** = 매월 상대적입니다.<br /><br /> **64** = 자동 시작.<br /><br /> **128** = 되풀이 됩니다.|  
|**frequency_interval**|**int**|**Frequency_type**에 의해 설정 된 빈도에 적용 되는 값입니다.|  
|**frequency_relative_interval**|**int**|배포 에이전트의 날짜입니다.<br /><br /> **1** = 첫 번째<br /><br /> **2** = 초<br /><br /> **4** = 세 번째<br /><br /> **8** = 네 번째.<br /><br /> **16** = 마지막|  
|**frequency_recurrence_factor**|**int**|**Frequency_type**에서 사용 하는 되풀이 비율입니다.|  
|**frequency_subday**|**int**|정의된 기간 동안 일정을 변경하는 빈도입니다.<br /><br /> **1** = 한 번<br /><br /> **2** = 초<br /><br /> **4** = 분<br /><br /> **8** = 시간|  
|**frequency_subday_interval**|**int**|**Frequency_subday**간격입니다.|  
|**active_start_time_of_day**|**int**|배포 에이전트가 처음으로 실행되도록 예약된 시간이며 HHMMSS 형식으로 표시됩니다.|  
|**active_end_time_of_day**|**int**|배포 에이전트가 마지막으로 실행되도록 예약된 시간이며 HHMMSS 형식으로 표시됩니다.|  
|**active_start_date**|**int**|배포 에이전트가 처음으로 실행되도록 예약된 날짜이며 YYYYMMDD 형식으로 표시됩니다.|  
|**active_end_date**|**int**|배포 에이전트가 마지막으로 실행되도록 예약된 날짜이며 YYYYMMDD 형식으로 표시됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
