---
title: getBlob 메서드(int)(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getBlob (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: a00275cb-0299-4a21-a518-2640598a5bbf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 959c051d1acd6659d57dff66a3b066fdf6728cd9
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80926403"
---
# <a name="getblob-method-int-sqlserverresultset"></a>getBlob 메서드(int)(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 행에서 지정된 열 인덱스의 값을 Java 프로그래밍 언어의 Blob 개체로 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.sql.Blob getBlob(int i)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *i*  
  
 열 인덱스를 나타내는 **int**입니다.  
  
## <a name="return-value"></a>Return Value  
 Blob 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getBlob 메서드는 java.sql.ResultSet 인터페이스의 getBlob 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [getBlob 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getblob-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
