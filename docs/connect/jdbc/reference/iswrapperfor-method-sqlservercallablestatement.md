---
title: isWrapperFor 메서드(SQLServerCallableStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 71156863-3588-453e-b5a5-0573b2c1bebf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2d023d42019b01c75d4f4552a4d840c3a7787263
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80926130"
---
# <a name="iswrapperfor-method-sqlservercallablestatement"></a>isWrapperFor 메서드(SQLServerCallableStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 문 개체가 지정된 인터페이스에 대한 래퍼인지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public boolean isWrapperFor(Class iface)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *iface*  
  
 인터페이스를 정의하는 **클래스**입니다.  
  
## <a name="return-value"></a>Return Value  
 이 개체가 인터페이스를 구현하거나 인터페이스를 구현하는 개체를 래핑하면 **true**이고, 그렇지 않으면 **false**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 [isWrapperFor](../../../connect/jdbc/reference/iswrapperfor-method-sqlservercallablestatement.md) 메서드와 [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlservercallablestatement.md) 메서드는 JDBC 4.0에서 도입된 java.sql.Wrapper 인터페이스에 의해 정의됩니다.  
  
 이 메서드가 **true**를 반환하는 경우 동일한 인수로 [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlservercallablestatement.md)을 호출하는 데 성공합니다.  
  
 자세한 내용은 [래퍼와 인터페이스](../../../connect/jdbc/wrappers-and-interfaces.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [unwrap 메서드 &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/unwrap-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 멤버](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement 클래스](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
