---
title: getHoldability 메서드(SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.getHoldability
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b1644791-c36a-4837-86c4-9299537ee1c2
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 6f7dfc9609443febe545bd3b6ac7a6cdf75e1756
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "67982934"
---
# <a name="getholdability-method-sqlserverconnection"></a>getHoldability 메서드(SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 개체를 사용하여 만든 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 유지 기능을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int getHoldability()  
```  
  
## <a name="return-value"></a>Return Value  
 다음 유지 기능 수준 중 하나가 들어 있는 **int** 값입니다.  
  
 HOLD_CURSORS_OVER_COMMIT  
  
 CLOSE_CURSORS_AT_COMMIT  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getHoldability 메서드는 java.sql.Connection 인터페이스의 getHoldability 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
