---
title: SQLServerParameterMetaData 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 546290e0-9411-4a2b-aa36-61251e70e9cf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 99a81b89c0707d4d278a886bd7bbcbceb58d6068
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923876"
---
# <a name="sqlserverparametermetadata-class"></a>SQLServerParameterMetaData 클래스
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  준비된 문 매개 변수의 메타데이터를 나타냅니다.  
  
 **패키지:** com.microsoft.sqlserver.jdbc  
  
 **확장:** java.lang.Object  
  
 **구현:** java.sql.ParameterMetaData  
  
## <a name="syntax"></a>구문  
  
```  
  
public class SQLServerParameterMetaData  
```  
  
## <a name="remarks"></a>설명  
 매개 변수 메타데이터를 검색하려면 준비된 문을 SET FMT ONLY를 사용하여 실행합니다. 호출 가능한 문에서는 sp_sproc_columns를 호출하여 프로시저 매개 변수의 이름과 메타데이터를 검색합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerParameterMetaData 멤버](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [JDBC 드라이버 API 참조](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
