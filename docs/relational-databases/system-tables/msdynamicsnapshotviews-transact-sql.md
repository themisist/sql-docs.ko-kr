---
title: MSdynamicsnapshotviews (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSdynamicsnapshotviews_TSQL
- MSdynamicsnapshotviews
dev_langs:
- TSQL
helpviewer_keywords:
- MSdynamicsnapshotviews system table
ms.assetid: 4fc1822a-5d6e-4034-a2e2-363210232d3b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cc0668cb67308110cfde23390c809c8867fb959a
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889909"
---
# <a name="msdynamicsnapshotviews-transact-sql"></a>MSdynamicsnapshotviews(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSdynamicsnapshotviews** 테이블은 스냅숏 에이전트에 의해 만들어진 모든 필터링 된 데이터 스냅숏 뷰를 추적 하며, SQL Server 에이전트 또는 스냅숏 에이전트의 비정상적인 종료 시 뷰를 정리 하기 위해 시스템에서 사용 됩니다. 이 테이블은 게시 및 구독 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**dynamic_snapshot_view_name**|**sysname**|필터링된 임시 데이터 스냅샷 뷰의 이름입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [복제 테이블&#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
