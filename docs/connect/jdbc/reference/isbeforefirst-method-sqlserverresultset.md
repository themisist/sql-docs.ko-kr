---
title: isBeforeFirst 메서드(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.isBeforeFirst
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e0e2bd28-6949-47dc-b9dd-145ffb337069
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5ab4b8639502f24f3bbe8946f19e5f5f2f197828
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80909789"
---
# <a name="isbeforefirst-method-sqlserverresultset"></a>isBeforeFirst 메서드(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  커서가 이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 첫 번째 행 앞에 있는지 여부를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public boolean isBeforeFirst()  
```  
  
## <a name="return-value"></a>Return Value  
 커서가 첫 번째 행 앞에 있으면 **true**입니다. 커서가 그 외의 위치에 있거나 결과 집합에 행이 들어 있지 않으면 **false**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 isBeforeFirst 메서드는 java.sql.ResultSet 인터페이스의 isBeforeFirst 메서드에 의해 지정됩니다.  
  
 이 메서드를 정방향 전용의 읽기 전용 커서를 비롯한 동적 커서와 함께 사용할 경우 selectMethod 연결 속성이 "cursor"로 설정되어 있으면 예외가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
