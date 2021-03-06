---
title: cancel 메서드(SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.cancel
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 276bd9c1-9329-4fc9-9622-ed673c83a12d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b19ff8669843e93dc7c220e3e6b48cbd5bab7d06
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923721"
---
# <a name="cancel-method-sqlserverstatement"></a>cancel 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) 개체에 의해 현재 실행되고 있는 SQL 문을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void cancel()  
```  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 cancel 메서드는 java.sql.Statement 인터페이스의 cancel 메서드에 의해 지정됩니다.  
  
 크기가 큰 정방향 전용의 읽기 전용 결과 집합을 하나만 생성하는 문을 실행할 경우 반환된 결과 집합에 포함된 처음 몇 개의 행에만 관심이 있는 경우가 있습니다. 이 경우 애플리케이션에서는 필요하지 않은 나머지 행을 삭제하는 데 필요한 처리 시간을 최소화하기 위해 결과 집합을 닫기 전에 관련 문 개체의 [cancel](../../../connect/jdbc/reference/cancel-method-sqlserverstatement.md) 메서드를 호출할 수 있습니다. 이 기술을 사용할지 여부를 결정할 때는 절약되는 처리 시간과 서버에서 실행을 취소하는 데 필요한 시간 및 추가 왕복을 적절히 고려해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
