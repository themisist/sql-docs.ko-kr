---
title: getResultSetHoldability 메서드(SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData,getResultSetHoldability
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f0bd6283-83ab-4a0a-b825-ec4cdccf03e1
author: MightyPen
ms.author: genemi
ms.openlocfilehash: f6fbf7a0cf66db8bbcc2f2f69d603bc5d32fb74d
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "67980374"
---
# <a name="getresultsetholdability-method-sqlserverdatabasemetadata"></a>getResultSetHoldability 메서드(SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 데이터베이스에 대한 결과 집합의 기본 유지 기능을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int getResultSetHoldability()  
```  
  
## <a name="return-value"></a>Return Value  
 기본 유지 기능을 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getResultSetHoldability 메서드는 java.sql.DatabaseMetaData 인터페이스의 getResultSetHoldability 메서드에 의해 지정됩니다.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 데이터베이스와 함께 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]를 사용할 경우 이 메서드는 1을 반환합니다. 이 값은 ResultSet.HOLD_CURSORS_OVER_COMMIT 상수와 같습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDatabaseMetaData 메서드](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 멤버](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 클래스](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
