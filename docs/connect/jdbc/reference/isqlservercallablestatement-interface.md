---
title: ISQLServerCallableStatement 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 030a1631-cfcd-41e0-beb5-47f93c01e8e0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0b34194a7c9f2d203e2a73006f2b2dade59dd0df
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80920723"
---
# <a name="isqlservercallablestatement-interface"></a>ISQLServerCallableStatement 인터페이스
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  JDBC의 호출 가능한 문을 나타냅니다. 이 인터페이스는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC 드라이버 3.0에서 추가되었습니다.  
  
 **패키지:** com.microsoft.sqlserver.jdbc  
  
 **확장:** java.sql.CallableStatement, [ISQLServerPreparedStatement](../../../connect/jdbc/reference/isqlserverpreparedstatement-interface.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
public interface ISQLServerCallableStatement  
```  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 [SQLServerCallableStatement 클래스](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)에 의해 구현됩니다.  
  
 이 인터페이스는 다음 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] 관련 메서드를 노출합니다.  
  
|방법|자세한 내용은 다음을 참조하세요.|  
|------------|-------------------------------|  
|microsoft.sql.DateTimeOffset getDateTimeOffset(int)|[getDateTimeOffset(int)](../../../connect/jdbc/reference/getdatetimeoffset-method-int.md)|  
|microsoft.sql.DateTimeOffset getDateTimeOffset(String)|[getDateTimeOffset(String)](../../../connect/jdbc/reference/getdatetimeoffset-method-string.md)|  
|void setDateTimeOffset(String, microsoft.sql.DateTimeOffset)|[setDateTimeOffset](../../../connect/jdbc/reference/setdatetimeoffset-method-sqlservercallablestatement.md)|  
  
## <a name="see-also"></a>참고 항목  
 [JDBC 드라이버 API 참조](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
