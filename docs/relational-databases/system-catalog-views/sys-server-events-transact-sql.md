---
title: sys. server_events (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_events_TSQL
- sys.server_events_TSQL
- server_events
- sys.server_events
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_events catalog view
ms.assetid: 996f6c9b-6426-4847-95d9-6b77541422be
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f5e753b2d5db8d75739f8e65c909f593f8b6e77
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85894956"
---
# <a name="sysserver_events-transact-sql"></a>sys.server_events(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  서버 수준의 이벤트 알림 또는 서버 수준 DDL 트리거를 실행시키는 각 이벤트당 한 개의 행을 포함합니다. 열 **object_id** 및 **형식** 은 서버 이벤트를 고유 하 게 식별 합니다.  

  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|실행할 서버 수준 이벤트 알림 또는 서버 수준 DDL 트리거의 ID입니다.|  
|**type**|**int**|이벤트 알림 또는 DDL 트리거를 발생시키는 이벤트의 유형입니다.|  
|**type_desc**|**nvarchar(60)**|DDL 트리거 또는 이벤트 알림을 발생시키는 이벤트에 대한 설명입니다.|  
|**event_group_type**|**int**|트리거나 이벤트 알림이 생성되는 이벤트 그룹 또는 Null(이벤트 그룹에 생성되지 않은 경우)입니다.|  
|**event_group_type_desc**|**nvarchar(60)**|트리거나 이벤트 알림이 생성되는 이벤트 그룹에 대한 설명 또는 Null(이벤트 그룹에 생성되지 않은 경우)입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;개체 카탈로그 뷰](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
