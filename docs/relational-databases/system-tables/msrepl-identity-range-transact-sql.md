---
title: MSrepl_identity_range (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSrepl_identity_range_TSQL
- MSrepl_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_identity_range system table
ms.assetid: 6e92a8e8-7667-4c98-b1c4-46735bac50d8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4aafc6415d968d25b7ba4e708985e72378f9d95f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889514"
---
# <a name="msrepl_identity_range-transact-sql"></a>MSrepl_identity_range(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSrepl_identity_range** 테이블은 id 범위 관리 지원을 제공 합니다. 이 테이블은 게시, 배포 및 구독 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**발행자**|**sysname**|게시자의 이름입니다.|  
|**publisher_db**|**sysname**|게시 데이터베이스의 이름입니다.|  
|**tablename**|**sysname**|테이블의 이름입니다.|  
|**identity_support**|**int**|자동 ID 범위 처리를 사용하는지 여부를 지정합니다. 0은 자동 ID 범위 처리를 사용하지 않음을 지정합니다.|  
|**next_seed**|**bigint**|자동 ID 범위를 사용하는 경우에 다음 범위의 시작 지점을 나타냅니다.|  
|**pub_range**|**bigint**|게시자 ID의 범위 크기입니다.|  
|**range**|**bigint**|조정 시 구독자에게 할당되는 연속 ID 값의 크기입니다.|  
|**max_identity**|**bigint**|ID 범위의 최대 경계입니다.|  
|**threshold**|**int**|ID 범위 임계값 비율입니다.|  
|**current_max**|**bigint**|할당할 수는 있지만 꼭 할당할 필요는 없는 현재 최대값입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
