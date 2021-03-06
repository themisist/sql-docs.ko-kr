---
title: MSarticles (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSarticles
- MSarticles_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSarticles system table
ms.assetid: 1acd79a5-b3e2-4161-9592-7acc2a41ba38
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6272b8370b461db0a7a2259be3de4d584ea8498
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890057"
---
# <a name="msarticles-transact-sql"></a>MSarticles(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **Msarticles** 테이블에는 게시자가 복제 하는 각 아티클에 대 한 행이 하나씩 포함 되어 있습니다. 이 테이블은 배포 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**publisher_id**|**smallint**|게시자의 ID입니다.|  
|**publisher_db**|**sysname**|게시자 데이터베이스의 이름입니다.|  
|**publication_id**|**int**|게시의 ID입니다.|  
|**문서**|**sysname**|아티클의 이름입니다.|  
|**article_id**|**int**|아티클의 ID입니다.|  
|**destination_object**|**sysname**|구독자에서 생성되는 테이블의 이름입니다.|  
|**source_owner**|**sysname**|게시자에서 원본 테이블의 스키마 이름입니다.|  
|**source_object**|**sysname**|아티클을 추가할 출처가 되는 원본 개체의 이름입니다.|  
|**한**|**nvarchar(255)**|아티클 설명입니다.|  
|**destination_owner**|**sysname**|구독자에서 생성된 테이블의 스키마 이름입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
