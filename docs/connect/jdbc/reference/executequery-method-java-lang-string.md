---
title: executeQuery 메서드(java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerPreparedStatement.executeQuery (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 610205c2-6bcd-426c-ad6f-9682551efdec
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 38e5a31ccaf493a8800f0e15abd1c21424db07c7
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "67954814"
---
# <a name="executequery-method-javalangstring"></a>executeQuery 메서드(java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 SQL 문을 실행하고 단일 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final java.sql.ResultSet executeQuery(java.lang.String sql)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sql*  
  
 SQL 문이 포함된 **문자열**입니다.  
  
## <a name="return-value"></a>Return Value  
 SQLServerResultSet 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 executeQuery 메서드는 java.sql.Statement 인터페이스의 executeQuery 메서드에 의해 지정됩니다.  
  
 이 메서드는 [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) 클래스에 있는 [executeQuery](../../../connect/jdbc/reference/executequery-method-sqlserverstatement.md) 메서드를 재정의합니다.  
  
 SQLServerPreparedStatement 개체에 대한 SQL 문은 개체가 만들어질 때 지정되므로 이 메서드를 호출하면 예외가 발생합니다.  
  
 지정된 SQL 문에서 단일 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체 이외의 개체를 생성하면 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)이 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [executeQuery 메서드 &#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/executequery-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 멤버](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement 클래스](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
