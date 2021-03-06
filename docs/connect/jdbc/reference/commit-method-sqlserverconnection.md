---
title: commit 메서드(SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.commit
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: c7346165-51bf-4844-b64c-29833c147236
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 50afbfa25052e0f602c486d011ce666a599372e0
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923585"
---
# <a name="commit-method-sqlserverconnection"></a>commit 메서드(SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이전의 커밋 또는 롤백 후에 변경된 모든 내용을 영구적으로 만들고, 이 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 개체에서 현재 보유 중인 데이터베이스 잠금을 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void commit()  
```  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 commit 메서드는 java.sql.Connection 인터페이스의 commit 메서드에 의해 지정됩니다.  
  
 이 메서드는 자동 커밋 모드가 해제된 경우에만 사용해야 합니다.  
  
 클라이언트에서 수동 트랜잭션을 시작한 다음 어떤 이유로 SQL Server에서 수동 트랜잭션을 롤백할 경우에는 이 메서드가 실패하고 예외가 발생합니다. 예를 들어 클라이언트에서 ROLLBACK TRANSACTION을 명시적으로 호출하는 저장 프로시저를 호출한 다음, commit 메서드를 호출하면 예외가 발생합니다. 또한 SQL Server에서 심각도가 16 이상으로 매우 높은 오류를 발생시켜 클라이언트에서 시작한 수동 트랜잭션을 롤백할 경우 이후에 commit 메서드를 호출하면 예외가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
