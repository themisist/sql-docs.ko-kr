---
title: Groups 컬렉션 (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Groups
- User::Groups
- Catalog::Groups
helpviewer_keywords:
- Groups collection [ADOX]
ms.assetid: 09aa7b0a-69d5-4564-80a7-20ad8189670f
author: rothja
ms.author: jroth
ms.openlocfilehash: e2b6e7b7669e0976cf47e5b4d5d2c827a824f919
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764854"
---
# <a name="groups-collection-adox"></a>Groups 컬렉션(ADOX)
카탈로그나 사용자의 모든 저장 된 [그룹](../../../ado/reference/adox-api/group-object-adox.md) 개체를 포함 합니다.  
  
## <a name="remarks"></a>설명  
 [카탈로그](../../../ado/reference/adox-api/catalog-object-adox.md) 의 **Groups** 컬렉션은 모든 카탈로그 그룹 계정을 나타냅니다. [사용자](../../../ado/reference/adox-api/user-object-adox.md) 에 대 한 **그룹** 컬렉션은 사용자가 속한 그룹만 나타냅니다.  
  
 **그룹** 컬렉션에 대 한 [APPEND](../../../ado/reference/adox-api/append-method-adox-groups.md) 메서드는 ADOX에 대해 고유 합니다. 다음을 수행할 수 있습니다.  
  
-   **Append** 메서드를 사용 하 여 컬렉션에 새 보안 그룹을 추가 합니다.  
  
 나머지 속성 및 메서드는 ADO 컬렉션의 표준입니다. 다음을 수행할 수 있습니다.  
  
-   [Item](../../../ado/reference/ado-api/item-property-ado.md) 속성을 사용 하 여 컬렉션의 그룹에 액세스 합니다.  
  
-   [Count](../../../ado/reference/ado-api/count-property-ado.md) 속성을 사용 하 여 컬렉션에 포함 된 그룹의 수를 반환 합니다.  
  
-   [Delete](../../../ado/reference/adox-api/delete-method-adox-collections.md) 메서드를 사용 하 여 컬렉션에서 그룹을 제거 합니다.  
  
-   [Refresh](../../../ado/reference/ado-api/refresh-method-ado.md) 메서드를 사용 하 여 현재 데이터베이스 스키마를 반영 하도록 컬렉션의 개체를 업데이트 합니다.  
  
> [!NOTE]
>  **그룹** 개체를 **사용자** 개체의 **groups** 컬렉션에 추가 하기 전에 추가 될 그룹과 동일한 [이름의](../../../ado/reference/adox-api/name-property-adox.md) **그룹** 개체가 **카탈로그**의 **groups** 컬렉션에 이미 존재 해야 합니다.  
  
 이 섹션에는 다음 항목이 포함 되어 있습니다.  
  
-   [Groups 컬렉션 속성, 메서드 및 이벤트](../../../ado/reference/adox-api/groups-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>참고 항목  
 [Catalog 개체 (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)   
 [Group 개체(ADOX)](../../../ado/reference/adox-api/group-object-adox.md)
