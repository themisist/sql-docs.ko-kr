---
title: 명령 구문 | Microsoft Docs
description: 명령 구문 및 저장 프로시저
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, commands
- commands [OLE DB]
- OLE DB Driver for SQL Server, stored procedures
- stored procedures [OLE DB], command syntax
author: pmasl
ms.author: pelopes
ms.openlocfilehash: 15d6d221c9e3435a3ba4c3f58c7d6b6e55314f29
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "68016125"
---
# <a name="command-syntax"></a>명령 구문
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  OLE DB Driver for SQL Server는 DBGUID_SQL 매크로로 지정된 명령 구문을 인식합니다. OLE DB Driver for SQL Server의 경우, 지정자는 ODBC SQL, ISO 및 [!INCLUDE[tsql](../../../includes/tsql-md.md)]이 모두 유효함을 나타냅니다. 예를 들어 다음 SQL 문은 ODBC SQL 이스케이프 시퀀스를 사용하여 LCASE 문자열 함수를 지정합니다.  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 LCASE는 문자열을 반환하고 모든 대문자를 소문자로 변환합니다. ISO 문자열 함수 LOWER도 동일한 작업을 수행하기 때문에 다음 SQL 문은 바로 위에 있는 ODBC 문에 해당하는 ISO 버전입니다.  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 명령 텍스트로 지정할 경우 SQL Server용 OLE DB 드라이버는 위의 두 가지 명령문 형식 모두를 문제 없이 처리합니다.  
  
## <a name="stored-procedures"></a>저장 프로시저  
 SQL Server용 OLE DB 드라이버 명령을 사용하여 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 저장 프로시저를 실행할 경우 명령 텍스트에 ODBC CALL 이스케이프 시퀀스를 사용해야 합니다. SQL Server용 OLE DB 드라이버는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]의 원격 프로시저 호출 메커니즘을 사용하여 명령 처리를 최적화합니다. 예를 들어 다음 중 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 형식보다는 ODBC SQL 문을 명령 텍스트로 사용하는 것이 좋습니다.  
  
-   ODBC SQL  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   Transact-SQL  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [명령](../../oledb/ole-db-commands/commands.md)  
  
  
