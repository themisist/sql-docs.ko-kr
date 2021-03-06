---
title: getSQLStateType 메서드(SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.getSQLStateType
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ee4d6751-68a3-4d04-831c-e6d704c59e63
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 762c22bbf2ed499fc2c0884014e374af17f60292
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80921945"
---
# <a name="getsqlstatetype-method-sqlserverdatabasemetadata"></a>getSQLStateType 메서드(SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  SQLException.getSQLState 메서드에서 반환된 SQLSTATE가 X/Open(현재는 Open Group이라고 함), SQL CLI, SQL99(JDBC 3.0) 또는 SQL:2003(JDBC 4.0) 중 무엇인지를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int getSQLStateType()  
```  
  
## <a name="return-value"></a>Return Value  
 다음 값 중 하나에 해당되는 SQLSTATE 형식을 나타내는 **int**입니다.  
  
-   Java Runtime Environment 버전 5.0의 경우: **xopenStates** 연결 속성이 **true**로 설정된 경우 이 메서드는 DatabaseMetaData.sqlStateXOpen을 반환합니다. 그렇지 않으면 DatabaseMetaData.sqlStateSQL99를 반환합니다.  
  
-   Java Runtime Environment 버전 6.0의 경우: **xopenStates** 연결 속성이 **true**로 설정된 경우 이 메서드는 DatabaseMetaData.sqlStateXOpen을 반환합니다. 그렇지 않으면 DatabaseMetaData.sqlStateSQL을 반환합니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getSQLStateType 메서드는 java.sql.DatabaseMetaData 인터페이스의 getSQLStateType 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDatabaseMetaData 메서드](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 멤버](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 클래스](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
