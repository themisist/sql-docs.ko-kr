---
title: 오류 인터페이스의 정보
description: OLE DB Driver for SQL Server는 OLE DB에서 정의된 오류 인터페이스 IErrorInfo, IErrorRecords 및 ISQLErrorInfo의 몇 가지 오류 및 상태 정보를 보고합니다.
ms.custom: ''
ms.date: 05/06/2020
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
author: pmasl
ms.author: pelopes
ms.openlocfilehash: f398cb4ca6cdeaa9484e01b5ca41ae28b7d9f095
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86003361"
---
# <a name="information-in-error-interfaces"></a>오류 인터페이스의 정보
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  SQL Server용 OLE DB 드라이버는 OLE DB에서 정의된 오류 인터페이스 **IErrorInfo**, **IErrorRecords** 및 **ISQLErrorInfo**의 몇 가지 오류 및 상태 정보를 보고합니다.  
  
 OLE DB Driver for SQL Server는 다음과 같은 **IErrorInfo** 멤버 함수를 지원합니다.  
  
|멤버 함수|Description|  
|---------------------|-----------------|  
|**GetDescription**|설명적인 오류 메시지 문자열입니다.|  
|**GetGUID**|오류를 정의한 인터페이스의 GUID입니다.|  
|**GetHelpContext**|지원되지 않습니다. 항상 0을 반환합니다.|  
|**GetHelpFile**|지원되지 않습니다. 항상 NULL을 반환합니다.|  
|**GetSource**|“SQL Server용 Microsoft OLE DB 드라이버” 문자열입니다.|  
  
 OLE DB Driver for SQL Server는 소비자가 사용할 수 있는 다음과 같은 **IErrorRecords** 멤버 함수를 지원합니다.  
  
|멤버 함수|Description|  
|---------------------|-----------------|  
|**GetBasicErrorInfo**|ERRORINFO 구조에 오류에 대한 기본 정보를 채웁니다. ERRORINFO 구조에는 오류에 대한 HRESULT 반환 값을 식별하는 멤버와 오류가 적용되는 공급자 및 인터페이스가 포함됩니다.|  
|**GetCustomErrorObject**|**ISQLErrorInfo** 및 [ISQLServerErrorInfo](https://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1) 인터페이스에 대한 참조를 반환합니다.|  
|**GetErrorInfo**|**IErrorInfo** 인터페이스에 대한 참조를 반환합니다.|  
|**GetErrorParameters**|OLE DB Driver for SQL Server는 **GetErrorParameters**를 통해 소비자에게 매개 변수를 반환하지 않습니다.|  
|**GetRecordCount**|사용할 수 있는 오류 레코드 수입니다.|  
  
 OLE DB Driver for SQL Server는 다음과 같은 **ISQLErrorInfo::GetSQLInfo** 매개 변수를 지원합니다.  
  
|매개 변수|Description|  
|---------------|-----------------|  
|*pbstrSQLState*|오류의 SQLSTATE 값을 반환합니다. SQLSTATE 값은 SQL-92, ODBC 및 ISO SQL, API 사양에서 정의됩니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 및 OLE DB Driver for SQL Server는 구현별 SQLSTATE 값을 정의하지 않았습니다.|  
|*plNativeError*|사용 가능한 경우 **master.dbo.sysmessages**의 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 오류 번호를 반환합니다. OLE DB Driver for SQL Server 데이터 원본을 성공적으로 초기화하면 원시 오류를 사용할 수 있습니다. 시도하기 전에 OLE DB Driver for SQL Server는 항상 0을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Errors](../../oledb/ole-db-errors/errors.md)  
  
  
