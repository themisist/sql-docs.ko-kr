---
title: setLoginTimeout 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setLoginTimeout
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b63d1cf4-dc1b-4e35-9a56-50436642eaaf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 83d6869075e296465ee9c60b0c5032407d4fe2da
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925759"
---
# <a name="setlogintimeout-method-sqlserverdatasource"></a>setLoginTimeout 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) 개체가 연결을 시도하는 동안 대기하는 시간(초)을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setLoginTimeout(int loginTimeout)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *loginTimeout*  
  
 대기할 시간(초)을 나타내는 **int** 값입니다. 0은 제한 시간이 기본 시스템 제한 시간(기본적을 15초로 지정됨)임을 의미합니다.  
  
## <a name="remarks"></a>설명  
 이 setLoginTimeout 메서드는 javax.sql.DataSource 인터페이스의 setLoginTimeout 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
