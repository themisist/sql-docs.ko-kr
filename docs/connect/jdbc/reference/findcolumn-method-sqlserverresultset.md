---
title: findColumn 메서드(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.findColumn
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7c29994a-0b53-420b-8a9b-82a9eef08587
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 56e01d155c90e5e57dc9c2add6f8fd3540892596
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80920945"
---
# <a name="findcolumn-method-sqlserverresultset"></a>findColumn 메서드(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체에서 지정된 열 이름과 일치하는 첫 번째 열의 인덱스를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int findColumn(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열의 이름이 포함된 **문자열**입니다.  
  
## <a name="return-value"></a>Return Value  
 열 인덱스를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 findColumn 메서드는 java.sql.ResultSet 인터페이스의 findColumn 메서드에 의해 지정됩니다.  
  
 같은 이름의 열이 여러 개 있으면 findColumn 메서드는 대/소문자를 구분하여 첫 번째로 일치하는 열을 반환합니다. 대/소문자까지 일치하는 열이 없으면 이 메서드는 대/소문자를 구분하지 않고 첫 번째로 일치하는 열을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
