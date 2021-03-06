---
title: InheritTypeEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- InheritTypeEnum
helpviewer_keywords:
- InheritTypeEnum enumeration [ADOX]
ms.assetid: c2f6ce79-c4b3-4d40-ac95-21025208f991
author: rothja
ms.author: jroth
ms.openlocfilehash: f420d7d49ad24188f5210001af1209427478f3f6
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82746676"
---
# <a name="inherittypeenum"></a>InheritTypeEnum
개체가 [SetPermissions](../../../ado/reference/adox-api/setpermissions-method-adox.md)로 설정 된 사용 권한을 상속 하는 방법을 지정 합니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|**adInheritBoth**|3|주 개체에 포함 된 개체와 기타 컨테이너는 모두 항목을 상속 합니다.|  
|**adInheritContainers**|2|주 개체에 포함 된 다른 컨테이너는 항목을 상속 합니다.|  
|**adInheritNone**|0|기본값 상속이 발생 하지 않습니다.|  
|**adInheritNoPropagate**|4|**AdInheritObjects** 및 **adInheritContainers** 플래그는 상속 된 항목으로 전파 되지 않습니다.|  
|**adInheritObjects**|1|컨테이너의 컨테이너가 아닌 개체는 권한을 상속 합니다.|  
  
## <a name="applies-to"></a>적용 대상  
 [SetPermissions 메서드(ADOX)](../../../ado/reference/adox-api/setpermissions-method-adox.md)
