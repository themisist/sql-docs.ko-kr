---
title: setFetchSize 메서드(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.setFetchSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 233bf4f8-4758-42d0-a80b-33e34fa78027
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5052d9830c3df97e8e491c38a3c606bbdfca1919
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80922323"
---
# <a name="setfetchsize-method-sqlserverresultset"></a>setFetchSize 메서드(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체에 추가 행이 필요할 때 데이터베이스에서 인출할 행 수에 관한 힌트를 JDBC 드라이버에 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setFetchSize(int rows)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rows*  
  
 가져올 행 수를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 setFetchSize 메서드는 java.sql.ResultSet 인터페이스의 setFetchSize 메서드에 의해 지정됩니다.  
  
 지정된 인출 크기가 0이면 JDBC 드라이버는 이 값을 무시하고 필요한 인출 크기를 예측합니다. 기본값은 해당 결과 집합을 만든 [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) 개체에 의해 설정됩니다. 인출 크기는 언제든지 변경할 수 있습니다.  
  
 이 메서드는 서버 커서의 블록 인출 크기를 변경하며, 다음에 JDBC 드라이버에서 sp_cursorfetch를 호출해야 할 때 적용됩니다. 인출 크기를 0으로 설정하면 현재 사용 중인 커서 유형의 기본 인출 크기가 복원됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
