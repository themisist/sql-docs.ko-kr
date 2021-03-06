---
title: sp_syscollector_delete_collection_item (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_syscollector_delete_collection_item
- sp_syscollector_delete_collection_item_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syscollector_delete_collecton_item
- data collector [SQL Server], stored procedures
ms.assetid: 9c2b0990-1d3d-4a59-94a0-3cca6fef4681
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f0753ed820012d0bbae1fb263b7881aad663ee45
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85892941"
---
# <a name="sp_syscollector_delete_collection_item-transact-sql"></a>sp_syscollector_delete_collection_item(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  컬렉션 집합에서 컬렉션 항목을 삭제합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_syscollector_delete_collection_item [[ @collection_item_id = ] collection_item_id ]  
    , [[ @name = ] 'name' ]   
```  
  
## <a name="arguments"></a>인수  
 [ @collection_item_id =] *collection_item_id*  
 컬렉션 항목의 고유 식별자입니다. *collection_item_id* 은 **int** 이며 기본값은 NULL입니다. *name* 이 NULL 인 경우 *collection_item_id* 에 값이 있어야 합니다.  
  
 [ @name =] '*name*'  
 컬렉션 항목의 이름입니다. *name* 은 **sysname** 이며 기본값은 NULL입니다. *collection_item_id* 가 NULL 이면 *이름* 에 값이 있어야 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>설명  
 sp_syscollector_delete_collection_item은 msdb 시스템 데이터베이스의 컨텍스트 내에서 실행되어야 합니다. 시스템 컬렉션 집합에서는 컬렉션 항목을 삭제할 수 없습니다.  
  
 이 작업을 수행하는 동안에는 컬렉션 항목을 포함하는 컬렉션 집합이 중지되고 다시 시작됩니다.  
  
## <a name="permissions"></a>사용 권한  
 이 프로시저를 실행하려면 dc_admin(EXECUTE 권한 있음) 고정 데이터베이스 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `MyCollectionItem1`이라는 컬렉션 항목을 삭제합니다.  
  
```  
USE msdb;  
GO  
EXEC sp_syscollector_delete_collection_item @name = 'MyCollectionItem1';  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 수집](../../relational-databases/data-collection/data-collection.md)   
 [Transact-sql&#41;sp_syscollector_create_collection_item &#40;](../../relational-databases/system-stored-procedures/sp-syscollector-create-collection-item-transact-sql.md)   
 [Transact-sql&#41;&#40;데이터 수집기 저장 프로시저](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [syscollector_collection_items&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/syscollector-collection-items-transact-sql.md)  
  
  
