---
title: CursorTypeEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CursorTypeEnum
helpviewer_keywords:
- CursorTypeEnum enumeration [ADO]
ms.assetid: ffc6e245-4471-42ae-84dd-e85bddfce983
author: rothja
ms.author: jroth
ms.openlocfilehash: 0af12cbad09990add1e5f42c05a68a0d249377fa
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763494"
---
# <a name="cursortypeenum"></a>CursorTypeEnum
[레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md) 개체에 사용 되는 커서의 유형을 지정 합니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|**adOpenDynamic**|2|동적 커서를 사용 합니다. 다른 사용자에의 한 추가, 변경 및 삭제 내용이 표시 되 고, 공급자가 지원 하지 않는 경우 책갈피를 제외 하 고 **레코드 집합** 을 통한 모든 이동 유형이 허용 됩니다.|  
|**adOpenForwardOnly**|0|기본값 앞 으로만 이동 가능한 커서를 사용 합니다. 레코드를 앞 으로만 스크롤할 수 있다는 점을 제외 하 고 정적 커서와 동일 합니다. 이렇게 하면 **레코드 집합**을 한 번만 통과 해야 하는 경우 성능이 향상 됩니다.|  
|**adOpenKeyset**|1|키 집합 커서를 사용 합니다. 다른 사용자가 삭제 하는 레코드는 **레코드 집합**에서 액세스할 수 없지만 다른 사용자가 추가 하는 레코드는 볼 수 없다는 점을 제외 하 고는 동적 커서와 같습니다. 다른 사용자의 데이터 변경 내용은 계속 표시 됩니다.|  
|**adOpenStatic**|3|는 데이터를 찾거나 보고서를 생성 하는 데 사용할 수 있는 레코드 집합의 정적 복사본 인 정적 커서를 사용 합니다. 다른 사용자가 추가, 변경 또는 삭제 하는 것은 표시 되지 않습니다.|  
|**adOpenUnspecified 되지 않음**|-1|는 커서의 형식을 지정 하지 않습니다.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 동급  
 Package: **com.ms.wfc.data**  
  
|상수|  
|--------------|  
|AdoEnums. CursorType|  
|AdoEnums. CursorType만|  
|AdoEnums. CursorType|  
|AdoEnums. CursorType|  
|AdoEnums. CursorType|  
  
## <a name="applies-to"></a>적용 대상  
 [CursorType 속성(ADO)](../../../ado/reference/ado-api/cursortype-property-ado.md)
