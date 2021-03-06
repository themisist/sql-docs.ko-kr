---
title: Member 개체 (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Member
helpviewer_keywords:
- Member object [ADO MD], members
ms.assetid: 3dedf755-0741-4c3f-8b4e-bff8ff8809c8
author: rothja
ms.author: jroth
ms.openlocfilehash: d4d512d651c8162124c935ffdb260c4abe4ecb14
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82753205"
---
# <a name="member-object-ado-md"></a>Member 개체(ADO MD)
큐브의 수준 멤버, 수준 멤버의 자식 또는 셀 집합의 축에 있는 위치의 멤버를 나타냅니다.  
  
## <a name="remarks"></a>설명  
 **멤버** 의 속성은 사용 되는 컨텍스트에 따라 달라 집니다. [CubeDef](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md) [수준의](../../../ado/reference/ado-md-api/level-object-ado-md.md) **멤버** 는 현재 **멤버**에서 계층의 다음 하위 수준에 있는 **멤버** 를 반환 하는 [Children](../../../ado/reference/ado-md-api/children-property-ado-md.md) 속성을 가집니다. [위치의](../../../ado/reference/ado-md-api/position-object-ado-md.md) **멤버** 에 대 한 **자식** 컬렉션은 항상 비어 있습니다. 또한 [Type](../../../ado/reference/ado-md-api/type-property-ado-md.md) 속성은 **수준의** **멤버** 에만 적용 됩니다.  
  
 **Position** 의 **멤버** 에는 [Cellset](../../../ado/reference/ado-md-api/cellset-object-ado-md.md): [DrilledDown](../../../ado/reference/ado-md-api/drilleddown-property-ado-md.md) 및 [ParentSameAsPrev](../../../ado/reference/ado-md-api/parentsameasprev-property-ado-md.md)를 표시할 때 유용 하 게 사용할 수 있는 두 가지 속성이 있습니다. **수준** **멤버** 에서 이러한 속성에 액세스 하는 경우 오류가 발생 합니다.  
  
 **수준** **멤버** 개체의 컬렉션 및 속성을 사용 하 여 다음을 수행할 수 있습니다.  
  
-   [Name](../../../ado/reference/ado-md-api/name-property-ado-md.md) 및 [UniqueName](../../../ado/reference/ado-md-api/uniquename-property-ado-md.md) 속성을 사용 하 여 **멤버** 를 식별 합니다.  
  
-   [Caption](../../../ado/reference/ado-md-api/caption-property-ado-md.md) 속성을 사용 하 여 **멤버** 를 표시할 때 사용할 문자열을 반환 합니다.  
  
-   [Description](../../../ado/reference/ado-md-api/description-property-ado-md.md) 속성을 사용 하 여 측정값 또는 수식 **멤버** 를 설명 하는 의미 있는 문자열을 반환 합니다.  
  
-   [유형](../../../ado/reference/ado-md-api/type-property-ado-md.md) 속성을 사용 하 여 **멤버** 의 특성을 결정 합니다.  
  
-   [Leveldepth](../../../ado/reference/ado-md-api/leveldepth-property-ado-md.md) 및 [LevelName](../../../ado/reference/ado-md-api/levelname-property-ado-md.md) 속성을 사용 하 여 **멤버** **수준** 에 대 한 정보를 가져옵니다.  
  
-   [부모](../../../ado/reference/ado-md-api/parent-property-ado-md.md) 및 [자식](../../../ado/reference/ado-md-api/children-property-ado-md.md) 속성을 사용 하 여 [계층](../../../ado/reference/ado-md-api/hierarchy-object-ado-md.md) 의 관련 **멤버** 를 가져옵니다.  
  
-   [ChildCount](../../../ado/reference/ado-md-api/childcount-property-ado-md.md) 속성을 사용 하 여 **멤버** 의 자식 수를 계산 합니다.  
  
-   표준 ADO [속성](../../../ado/reference/ado-api/properties-collection-ado.md) 컬렉션을 사용 하 여 **수준** 개체에 대 한 추가 정보를 가져올 수 있습니다.  
  
 [축](../../../ado/reference/ado-md-api/axis-object-ado-md.md)에 있는 **위치** **멤버** 의 컬렉션 및 속성을 사용 하 여 다음을 수행할 수 있습니다.  
  
-   [Name](../../../ado/reference/ado-md-api/name-property-ado-md.md) 및 [UniqueName](../../../ado/reference/ado-md-api/uniquename-property-ado-md.md) 속성을 사용 하 여 **멤버** 를 식별 합니다.  
  
-   [Caption](../../../ado/reference/ado-md-api/caption-property-ado-md.md) 속성을 사용 하 여 **멤버** 를 표시할 때 사용할 문자열을 반환 합니다.  
  
-   [Description](../../../ado/reference/ado-md-api/description-property-ado-md.md) 속성을 사용 하 여 측정값 또는 수식 **멤버** 를 설명 하는 의미 있는 문자열을 반환 합니다.  
  
-   [Leveldepth](../../../ado/reference/ado-md-api/leveldepth-property-ado-md.md) 및 [LevelName](../../../ado/reference/ado-md-api/levelname-property-ado-md.md) 속성을 사용 하 여 **멤버** **수준** 에 대 한 정보를 가져옵니다.  
  
-   [ChildCount](../../../ado/reference/ado-md-api/childcount-property-ado-md.md) 속성을 사용 하 여 **멤버** 의 자식 수를 계산 합니다.  
  
-   [DrilledDown](../../../ado/reference/ado-md-api/drilleddown-property-ado-md.md) 속성을 사용 하 여이 **멤버**바로 뒤의 **축** 에 자식이 하나 이상 있는지 여부를 확인 합니다.  
  
-   [ParentSameAsPrev](../../../ado/reference/ado-md-api/parentsameasprev-property-ado-md.md) 속성을 사용 하 여이 **멤버** 의 부모가 바로 앞에 있는 **멤버**의 부모와 같은지 여부를 확인 합니다.  
  
-   표준 ADO [속성](../../../ado/reference/ado-api/properties-collection-ado.md) 컬렉션을 사용 하 여 **수준** 개체에 대 한 추가 정보를 가져올 수 있습니다.  
  
 **속성** 컬렉션에는 공급자가 제공한 속성이 포함 되어 있습니다. 다음 표에서는 사용할 수 있는 속성을 보여 줍니다. 실제 속성 목록은 공급자의 구현에 따라 다를 수 있습니다. 사용 가능한 속성의 전체 목록은 공급자 설명서를 참조 하세요.  
  
|이름|설명|  
|----------|-----------------|  
|CatalogName|이 큐브가 속한 카탈로그의 이름입니다.|  
|ChildrenCardinality|멤버의 자식 수입니다.|  
|CubeName|큐브 이름입니다.|  
|설명|멤버에 대 한 의미 있는 설명입니다.|  
|DimensionUniqueName|[차원의](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)명확 하지 않은 이름입니다.|  
|HierarchyUniqueName|계층의 모호 하지 않은 이름입니다.|  
|LevelNumber|계층의 수준과 루트 사이의 거리입니다.|  
|LevelUniqueName|수준의 명확 하지 않은 이름입니다.|  
|MemberCaption|멤버에 연결된 레이블 또는 캡션입니다.|  
|MemberGUID|멤버의 GUID입니다.|  
|MemberName|멤버의 이름입니다.|  
|MemberOrdinal|멤버의 서 수 번호입니다.|  
|MemberType|멤버의 유형입니다.|  
|MemberUniqueName|멤버의 모호 하지 않은 이름입니다.|  
|ParentCount|이 멤버의 부모 수를 나타내는 수입니다.|  
|ParentLevel|멤버 부모의 수준 번호입니다.|  
|ParentUniqueName|멤버 부모의 모호 하지 않은 이름입니다.|  
|SchemaName|이 큐브가 속한 스키마의 이름입니다.|  
  
 이 섹션에는 다음 항목이 포함 되어 있습니다.  
  
-   [속성, 메서드 및 이벤트](../../../ado/reference/ado-md-api/member-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>참고 항목  
 [Catalog 예제 (VB)](../../../ado/reference/ado-md-api/catalog-example-vb.md)   
 [Members 컬렉션 (ADO MD)](../../../ado/reference/ado-md-api/members-collection-ado-md.md)   
 [Properties 컬렉션(ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
