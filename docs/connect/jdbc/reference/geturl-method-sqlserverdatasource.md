---
title: getURL 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getURL
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: dd0d5d2c-91fe-4b0f-a162-69d898ba176e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2ed41c600f0fc7a82f1f9a4ec3f512e96839191d
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80910559"
---
# <a name="geturl-method-sqlserverdatasource"></a>getURL 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  데이터 원본에 연결하는 데 사용되는 URL을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.lang.String getURL()  
```  
  
## <a name="return-value"></a>Return Value  
 URL을 포함하는 **문자열**입니다.  
  
## <a name="remarks"></a>설명  
 보안을 강화하려면 [setURL](../../../connect/jdbc/reference/seturl-method-sqlserverdatasource.md) 메서드에 제공되는 URL에 암호를 포함하지 말아야 합니다. 이는 타사 Java 애플리케이션 서버가 URL 속성에 설정된 값을 데이터 원본 구성 사용자 인터페이스에 표시하는 경우가 매우 많기 때문입니다. 대신 [setPassword](../../../connect/jdbc/reference/setpassword-method-sqlserverdatasource.md) 메서드를 사용하여 암호 값을 설정하세요. 데이터 원본에 설정된 암호는 Java 애플리케이션 서버가 구성 사용자 인터페이스에 표시하지 않습니다.  
  
> [!NOTE]  
>  getURL 메서드를 호출하기 전에 setURL 메서드를 호출하지 않은 경우 getURL은 기본값인 “jdbc:sqlserver://”를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
