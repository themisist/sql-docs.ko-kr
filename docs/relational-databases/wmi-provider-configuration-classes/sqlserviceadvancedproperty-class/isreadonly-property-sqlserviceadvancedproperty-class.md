---
title: IsReadOnly 속성 (SqlServiceAdvancedProperty)
ms.custom: seo-lt-2019
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- IsReadOnly Property (SqlServiceAdvancedProperty Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- IsReadOnly property
ms.assetid: 9672e70f-1d8c-4133-ac73-3b5733a1c4ee
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 031ffc6a0efc9a339ca40a83aee14e73d0c91d8d
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85880542"
---
# <a name="isreadonly-property-sqlserviceadvancedproperty-class"></a>IsReadOnly 속성(SqlServiceAdvancedProperty 클래스)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  고급 속성이 읽기 전용인지 여부를 지정하는 부울 속성을 가져오거나 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.IsReadOnly [= value]  
```  
  
## <a name="parts"></a>부분  
 *object*  
 고급 속성을 나타내는 [SqlServiceAdvancedProperty 클래스](../../../relational-databases/wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) 개체입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 고급 속성이 읽기 전용인지 여부를 지정하는 부울 값입니다. **true** 는 고급 속성이 읽기 전용임을 나타내고 **false** 는 고급 속성을 수정할 수 있음을 나타냅니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [서비스 시작 및 중지](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
