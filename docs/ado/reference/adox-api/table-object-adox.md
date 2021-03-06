---
title: Table 개체 (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Table
helpviewer_keywords:
- Table object [ADOX]
ms.assetid: a6d74000-0828-49ba-850a-63da865f8802
author: rothja
ms.author: jroth
ms.openlocfilehash: bcebe14b7b989e584539dd3f92fd8ea676ebd48a
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763304"
---
# <a name="table-object-adox"></a>테이블 개체(ADOX)
열, 인덱스 및 키를 포함 하는 데이터베이스 테이블을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 다음 코드는 새 **테이블**을 만듭니다.  
  
```  
Dim obj As New Table  
```  
  
 **Table** 개체의 속성 및 컬렉션을 사용 하 여 다음을 수행할 수 있습니다.  
  
-   [Name 속성 (ADOX)](../../../ado/reference/adox-api/name-property-adox.md) 속성을 사용 하 여 테이블을 식별 합니다.  
  
-   [유형 속성 (테이블) (ADOX)](../../../ado/reference/adox-api/type-property-table-adox.md) 속성을 사용 하 여 테이블 유형을 결정 합니다.  
  
-   [ADOX (Columns collection)](../../../ado/reference/adox-api/columns-collection-adox.md) 컬렉션을 사용 하 여 테이블의 데이터베이스 열에 액세스 합니다.  
  
-   [인덱스 컬렉션 (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)을 사용 하 여 테이블의 인덱스에 액세스 합니다.  
  
-   [키 컬렉션 (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)을 사용 하 여 테이블의 키에 액세스 합니다.  
  
-   [ParentCatalog 속성 (ADOX)](../../../ado/reference/adox-api/parentcatalog-property-adox.md) 속성을 사용 하 여 테이블을 소유 하는 카탈로그를 지정 합니다.  
  
-   [DateCreated 속성 (adox)](../../../ado/reference/adox-api/datecreated-property-adox.md) 및 [DATEMODIFIED Property (adox)](../../../ado/reference/adox-api/datemodified-property-adox.md) 속성을 사용 하 여 날짜 정보를 반환 합니다.  
  
-   [Properties collection (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md) 컬렉션을 사용 하 여 공급자별 테이블 속성에 액세스 합니다.  
  
> [!NOTE]
>  데이터 공급자가 **테이블** 개체의 일부 속성을 지원 하지 않을 수 있습니다. 공급자가 지원 하지 않는 속성에 대 한 값을 설정 하면 오류가 발생 합니다. 새 **테이블** 개체의 경우 개체가 컬렉션에 추가 되 면 오류가 발생 합니다. 기존 개체의 경우 속성을 설정할 때 오류가 발생 합니다.  
>   
>  **테이블** 개체를 만들 때 선택적 속성에 대해 적절 한 기본값이 있으면 공급자가 속성을 지원 하지 않을 수 있습니다. 공급자가 지 원하는 속성에 대 한 자세한 내용은 공급자 설명서를 참조 하십시오.  
  
 이 섹션에는 다음 항목이 포함 되어 있습니다.  
  
-   [Table 개체 속성, 메서드 및 이벤트](../../../ado/reference/adox-api/table-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>참고 항목  
 [Catalog ActiveConnection 속성 예제 (VB)](../../../ado/reference/adox-api/catalog-activeconnection-property-example-vb.md)   
 [Columns 및 Tables Append 메서드, Name 속성 예제 (VB)](../../../ado/reference/adox-api/columns-and-tables-append-methods-name-property-example-vb.md)   
 [Connection Close 메서드, Table Type 속성 예제 (VB)](../../../ado/reference/adox-api/connection-close-method-table-type-property-example-vb.md)   
 [Keys Append 메서드, Key Type, RelatedColumn, RelatedTable 및 UpdateRule 속성 예제 (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [ParentCatalog 속성 예제 (VB)](../../../ado/reference/adox-api/parentcatalog-property-example-vb.md)   
 [Columns 컬렉션 (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)   
 [Indexes 컬렉션 (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)   
 [Keys 컬렉션 (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)   
 [Properties 컬렉션 (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)   
 [Tables 컬렉션(ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)
