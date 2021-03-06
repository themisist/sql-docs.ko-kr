---
title: AbsolutePage 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::AbsolutePage
helpviewer_keywords:
- AbsolutePage property [ADO]
ms.assetid: ddb58a35-ec3a-423c-a504-3c65e62c23d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0da08a0c51c8d4d89329bbe9c36cacd7979c1e71
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82747545"
---
# <a name="absolutepage-property-ado"></a>AbsolutePage 속성(ADO)
현재 레코드가 있는 페이지를 나타냅니다.  
  
## <a name="settings-and-return-values"></a>설정 및 반환 값  
 32 비트 코드의 경우 1에서[PageCount](../../../ado/reference/ado-api/pagecount-property-ado.md)( [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md) 개체)의 페이지 수 까지의 **Long** 값을 설정 또는 반환 하거나 [positionenum](../../../ado/reference/ado-api/positionenum.md) 값 중 하나를 반환 합니다.  
  
 64 비트 코드의 경우 64 비트 값의 저장소에 대해 제공 하는 데이터 형식을 사용 합니다. 예를 들어, **Long** 또는 dbordinal과 같은 64 비트 길이를 사용할 수 있는 다른 값을 사용할 수 있습니다. **Positionenum** 값은 32 비트 길이로 제한 되므로 사용 하지 마십시오.  
  
## <a name="remarks"></a>설명  
 이 속성을 사용 하 여 현재 레코드가 있는 페이지 번호를 식별할 수 있습니다. [Pagesize](../../../ado/reference/ado-api/pagesize-property-ado.md) 속성을 사용 하 여 레코드 **집합** 개체의 전체 행 집합 수를 논리적으로 여러 페이지로 나눕니다. 각 페이지에는 **pagesize** 와 동일한 레코드 수가 있습니다. 마지막 페이지는 레코드 수가 적을 수 있습니다. 공급자는이 속성을 사용할 수 있는 적절 한 기능을 지원 해야 합니다.  
  
-   **AbsolutePage** 속성을 가져오거나 설정 하는 경우 ADO는 다음과 같이 [AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md) 속성과 [PageSize](../../../ado/reference/ado-api/pagesize-property-ado.md) 속성을 함께 사용 합니다.  
  
-   **AbsolutePage**를 가져오기 위해 ADO는 먼저 **AbsolutePosition**를 검색 한 다음 **PageSize**로 나눕니다.  
  
-   **AbsolutePage**를 설정 하기 위해 ADO는 **AbsolutePosition** 를 새 **AbsolutePage** **값으로 이동** 하 고 값에 1을 더 합니다. 따라서 **AbsolutePage** 를 성공적으로 설정한 후 **레코드 집합** 의 현재 위치는 해당 페이지의 첫 번째 레코드입니다.  
  
 **AbsolutePosition** 속성 처럼 **AbsolutePage** 은 1부터 시작 하 고 현재 레코드가 **레코드 집합**의 첫 번째 레코드인 경우 1과 같습니다. 특정 페이지의 첫 번째 레코드로 이동 하려면이 속성을 설정 합니다. **PageCount** 속성에서 총 페이지 수를 가져옵니다.  
  
## <a name="applies-to"></a>적용 대상  
 [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>참고 항목  
 [AbsolutePage, PageCount 및 PageSize 속성 예제 (VB)](../../../ado/reference/ado-api/absolutepage-pagecount-and-pagesize-properties-example-vb.md)   
 [AbsolutePage, PageCount 및 PageSize 속성 예제 (VC + +)](../../../ado/reference/ado-api/absolutepage-pagecount-and-pagesize-properties-example-vc.md)   
 [AbsolutePosition 속성 (ADO)](../../../ado/reference/ado-api/absoluteposition-property-ado.md)   
 [PageCount 속성 (ADO)](../../../ado/reference/ado-api/pagecount-property-ado.md)   
 [PageSize 속성(ADO)](../../../ado/reference/ado-api/pagesize-property-ado.md)
