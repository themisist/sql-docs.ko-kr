---
title: Type 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Parameter::Type
- Field20::Type
helpviewer_keywords:
- Type property [ADO]
ms.assetid: 8a4c079f-9f4f-4545-801d-85983b8db71e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bfa47120814058adbc5c2e5f3650a79b2202afb
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243184"
---
# <a name="type-property-ado"></a>Type 속성(ADO)
[매개 변수](../../../ado/reference/ado-api/parameter-object.md), [필드](../../../ado/reference/ado-api/field-object.md)또는 [속성](../../../ado/reference/ado-api/property-object-ado.md) 개체의 작동 유형 또는 데이터 형식을 나타냅니다.  
  
## <a name="settings-and-return-values"></a>설정 및 반환 값  
 [DataTypeEnum](../../../ado/reference/ado-api/datatypeenum.md) 값을 설정 하거나 반환 합니다.  
  
## <a name="remarks"></a>설명  
 **매개 변수** 개체의 경우 **Type** 속성은 읽기/쓰기가 됩니다. [레코드](../../../ado/reference/ado-api/record-object-ado.md)의 [Fields](../../../ado/reference/ado-api/fields-collection-ado.md) 컬렉션에 추가 된 새 **field** 개체의 경우 **필드** 의 [Value](../../../ado/reference/ado-api/value-property-ado.md) 속성을 지정 하 고 데이터 공급자가 **Fields** 컬렉션의 [Update](../../../ado/reference/ado-api/update-method.md) 메서드를 호출 하 여 새 **필드** 를 성공적으로 추가한 후에만 **형식이** 읽기/쓰기입니다.  
  
 다른 모든 개체의 경우 **형식** 속성은 읽기 전용입니다.  
  
## <a name="applies-to"></a>적용 대상  

:::row:::
    :::column:::
        [Field 개체](../../../ado/reference/ado-api/field-object.md)  
    :::column-end:::
    :::column:::
        [Parameter 개체](../../../ado/reference/ado-api/parameter-object.md)  
    :::column-end:::
    :::column:::
        [속성 개체(ADO)](../../../ado/reference/ado-api/property-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>참고 항목  
 [Type 속성 예제 (필드) (VB)](../../../ado/reference/ado-api/type-property-example-field-vb.md)   
 [Type 속성 예제 (속성) (VC + +)](../../../ado/reference/ado-api/type-property-example-property-vc.md)   
 [RecordType 속성 (ADO)](../../../ado/reference/ado-api/recordtype-property-ado.md)   
 [Type 속성(ADO 스트림)](../../../ado/reference/ado-api/type-property-ado-stream.md)
