---
title: setSavepoint 메서드(java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.setSavepoint (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 1cf15ec4-d9d9-4ab3-bfee-2ea43ff609a6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d7af636bd72c3c46a0f327a48bad644c8b4344b2
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925015"
---
# <a name="setsavepoint-method-javalangstring"></a>setSavepoint 메서드(java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  현재 트랜잭션에 지정된 이름의 저장점을 만들고 이 저장점을 나타내는 새 [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.sql.Savepoint setSavepoint(java.lang.String sName)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sName*  
  
 저장점의 이름이 들어 있는 **문자열** 값입니다.  
  
## <a name="return-value"></a>Return Value  
 SavePoint 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 setSavePoint 메서드는 java.sql.Connection 인터페이스의 setSavePoint 메서드에 의해 지정됩니다.  
  
 *sName* 인수는 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]에 의해 자동으로 이스케이프됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [setSavepoint 메서드(SQLServerConnection)](../../../connect/jdbc/reference/setsavepoint-method-sqlserverconnection.md)   
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
