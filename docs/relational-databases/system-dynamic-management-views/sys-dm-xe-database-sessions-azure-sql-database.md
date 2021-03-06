---
title: dm_xe_database_sessions (Azure SQL Database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.service: sql-database
ms.reviewer: ''
ms.topic: language-reference
ms.assetid: 33ea5179-16bb-4abd-96cc-9bc696e80987
author: CarlRabeler
ms.author: carlrab
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: ccb292c21cda8a335f1630b08d462f183a1f25e1
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85675766"
---
# <a name="sysdm_xe_database_sessions-azure-sql-database"></a>sys.dm_xe_database_sessions(Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  세션 이벤트에 대한 정보를 반환합니다. 이벤트는 불연속 실행 지점입니다. 조건자를 이벤트에 적용하여 이벤트가 필요한 정보를 포함하지 않을 경우 발생하지 않도록 할 수 있습니다.  
  
||  
|-|  
|**적용**대상: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 이상 버전.|  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8)**|이벤트 세션의 메모리 주소입니다. Null을 허용하지 않습니다.|  
|event_name|**nvarchar(60)**|동작이 바인딩된 이벤트의 이름입니다. Null을 허용하지 않습니다.|  
|event_package_guid|**uniqueidentifier**|이벤트가 포함된 패키지의 GUID입니다. Null을 허용하지 않습니다.|  
|event_predicate|**nvarchar(2048)**|이벤트에 적용되는 조건자 트리의 XML 표현입니다. Null을 허용합니다.|  
  
## <a name="permissions"></a>사용 권한  
 VIEW DATABASE STATE 권한이 필요합니다.  
  
### <a name="relationship-cardinalities"></a>관계 카디널리티  
2015-07-13의 경우 dm_xe_objects ' Xevent '는 이름에 ' _database '이 포함 되지 않은 이러한 Dmv Dmv 중 하나입니다. 다음 표의 오른쪽 열에는 오타가 나 오류가 없습니다. Microsoft SQL Server 및 Azure SQL Database에서 이름이 동일 합니다.  
  
|시작|대상|관계|  
|--------|------|----------------|  
|dm_xe_database_session_events. event_session_address|dm_xe_database_sessions. 주소|다 대 일|  
|dm_xe_database_session_events. event_package_guid, dm_xe_database_session_events event_name|sys.dm_xe_objects.name, sys.dm_xe_objects.package_guid|다 대 일|  
  
## <a name="see-also"></a>참고 항목  
[Azure SQL Database 확장 이벤트](https://azure.microsoft.com/documentation/articles/sql-database-xevent-db-diff-from-svr/)  
[확장 이벤트](../../relational-databases/extended-events/extended-events.md)  
  
 
