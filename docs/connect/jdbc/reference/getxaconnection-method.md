---
title: getXAConnection 메서드() | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerXADataSource.getXAConnection ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b2710613-78b1-438f-b996-c7ae6f34381a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4c4e5b96ed5d008e374884597197a735ec72f767
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80910161"
---
# <a name="getxaconnection-method-"></a>getXAConnection 메서드()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  분산 트랜잭션에 사용할 수 있는 실제 데이터베이스 연결을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public javax.sql.XAConnection getXAConnection()  
```  
  
## <a name="return-value"></a>Return Value  
 XAConnection 개체입니다.  
  
## <a name="exceptions"></a>예외  
 java.sql.SQLException  
  
## <a name="remarks"></a>설명  
 이 getXAConnection 메서드는 javax.sql.XADataSource 인터페이스의 getXAConnection 메서드에 의해 지정됩니다.  
  
> [!NOTE]  
>  이 메서드는 일반적으로 XA 연결 풀 구현에서 호출되며 일반적인 JDBC 애플리케이션 코드에서는 호출되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [getXAConnection 메서드(SQLServerXADataSource)](../../../connect/jdbc/reference/getxaconnection-method-sqlserverxadatasource.md)   
 [SQLServerXADataSource 메서드](../../../connect/jdbc/reference/sqlserverxadatasource-methods.md)   
 [SQLServerXADataSource 멤버](../../../connect/jdbc/reference/sqlserverxadatasource-members.md)   
 [SQLServerXADataSource 클래스](../../../connect/jdbc/reference/sqlserverxadatasource-class.md)  
  
  
