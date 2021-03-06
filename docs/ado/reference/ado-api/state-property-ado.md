---
title: State 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Command25::State
helpviewer_keywords:
- State property [ADO]
ms.assetid: 0b993bac-2653-40b1-bcbb-5b57b6aae2bf
author: rothja
ms.author: jroth
ms.openlocfilehash: f4fa19bf21764437d3713c434e288b3bb3a3d25d
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242573"
---
# <a name="state-property-ado"></a>State 속성(ADO)
개체의 상태가 열리거나 닫혀 있는지 여부에 관계 없이 모든 개체를 나타냅니다. 개체가 비동기 메서드를 실행 하는 경우 개체의 현재 상태에서 연결, 실행 또는 검색 하는지 여부를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 [ObjectStateEnum](../../../ado/reference/ado-api/objectstateenum.md) 값이 될 수 있는 **Long** 값을 반환 합니다. 기본값은 **adStateClosed**입니다.  
  
## <a name="remarks"></a>설명  
 **상태** 속성을 사용 하 여 언제 든 지 지정 된 개체의 현재 상태를 확인할 수 있습니다.  
  
 개체의 **State** 속성은 값의 조합을 가질 수 있습니다. 예를 들어 문이 실행 되는 경우이 속성에는 **Adstateopen** 및 **adstateopen**의 결합 된 값이 포함 됩니다.  
  
 **상태** 속성은 읽기 전용입니다.  
  
## <a name="applies-to"></a>적용 대상  

:::row:::
    :::column:::
        [명령 개체(ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
        [연결 개체(ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
    :::column-end:::
    :::column:::
        [레코드 개체(ADO)](../../../ado/reference/ado-api/record-object-ado.md)  
        [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
    :::column-end:::
    :::column:::
        [스트림 개체(ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>참고 항목  
 [ConnectionString, ConnectionTimeout 및 State 속성 예제 (VB)](../../../ado/reference/ado-api/connectionstring-connectiontimeout-and-state-properties-example-vb.md)   
 [ConnectionString, ConnectionTimeout 및 State 속성 예제 (VC + +)](../../../ado/reference/ado-api/connectionstring-connectiontimeout-and-state-properties-example-vc.md)   
