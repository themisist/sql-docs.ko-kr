---
title: MScached_peer_lsns (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MScached_peer_lsns_TSQL
- MScached_peer_lsns
dev_langs:
- TSQL
helpviewer_keywords:
- MScached_peer_lsns system table
ms.assetid: f8b6089a-0230-45f9-8c34-9fe0d2a3a74e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a4a6aa14106caf45aaac4e0432705d365022eec
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890041"
---
# <a name="mscached_peer_lsns-transact-sql"></a>MScached_peer_lsns(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MScached_peer_lsns** 테이블은 피어 투 피어 복제에서 지정 된 구독자에 게 반환할 명령을 결정 하는 데 사용 되는 트랜잭션 로그의 LSN 값을 추적 하는 데 사용 됩니다. 이 테이블은 배포 데이터베이스에 저장됩니다.  
  
## <a name="definition"></a>정의  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|배포 에이전트의 ID입니다.|  
|**송신자**|**sysname**|원래 게시자의 이름입니다.|  
|**originator_db**|**sysname**|원래 게시 데이터베이스의 이름입니다.|  
|**originator_publication_id**|**int**|원래 게시를 식별합니다.|  
|**originator_db_version**|**int**|원래 데이터베이스의 버전 번호를 식별합니다.|  
|**originator_lsn**|**varbinary(16)**|원래 트랜잭션의 LSN입니다.|  
  
## <a name="remarks"></a>설명  
 LSN 값은 삽입 직후에만 사용되고 그 의미가 시스템에서 유지되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
