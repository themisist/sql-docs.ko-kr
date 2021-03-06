---
title: sys. dm_exec_dms_services (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2019
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- DM_EXEC_DMS_SERVICES_TSQL
- SYS.DM_EXEC_DMS_SERVICES_TSQL
- DM_EXEC_DMS_SERVICES
dev_langs:
- TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- dm_exec_dms_services management view
- sys.dm_exec_dms_services management view
ms.assetid: 6ac47eef-4293-46b8-8555-07a614837504
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: d1b3171f1b5405cc251d15759ad6f6a7a134fadb
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82821280"
---
# <a name="sysdm_exec_dms_services-transact-sql"></a>sys. dm_exec_dms_services (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  PolyBase 계산 노드에서 실행 되는 모든 DMS 서비스에 대 한 정보를 저장 합니다. 서비스 인스턴스당 하나의 행을 나열 합니다.  
  
|열 이름|데이터 형식|설명|범위|  
|-----------------|---------------|-----------------|-----------|  
|dms_core_id|`int`|DMS 코어와 연결 된 고유 숫자 id입니다. 이 보기의 키입니다.|고유 ID입니다.|  
|compute_node_id|`int`|이 DMS 서비스가 실행 되 고 있는 노드의 ID입니다.|[Dm_exec_compute_nodes &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-nodes-transact-sql.md)에서 *compute_node_id* 를 참조 하세요.|  
|상태|`nvarchar(32)`|DMS 서비스의 현재 상태입니다.||
|compute_pool_id|`int`|풀에 대 한 고유 식별자입니다.|

## <a name="see-also"></a>참고 항목  
 [동적 관리 뷰를 사용한 PolyBase 문제 해결](https://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [Transact-sql&#41;&#40;동적 관리 뷰 및 함수](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Transact-sql&#41;&#40;데이터베이스 관련 동적 관리 뷰](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  
