---
title: updateRef 메서드(int, java.sql.Ref) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateRef (int, java.sql.Ref)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: eab3ebae-3f68-4303-869a-fee06e3a9c71
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: acdff5d46b8b2be5c060688353b43732b2a01b79
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80919711"
---
# <a name="updateref-method-int-javasqlref"></a>updateRef 메서드(int, java.sql.Ref)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  열 인덱스가 지정된 경우 지정된 열을 java.sql.Ref 값으로 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void updateRef(int columnIndex,  
                      java.sql.Ref x)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnIndex*  
  
 열 인덱스를 나타내는 **int**입니다.  
  
 *x*  
  
 Ref 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 updateRef 메서드는 java.sql.ResultSet 인터페이스의 updateRef 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [updateRef 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateref-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
