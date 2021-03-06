---
title: 시퀀스 유형 일치 | Microsoft Docs
description: XQuery 식에서 반환 된 시퀀스 유형을 특정 유형과 일치 시키는 방법에 대해 알아봅니다.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- sequence type matching [XQuery]
- XQuery, sequence type matching
ms.assetid: 8c56fb69-ca04-4aba-b55a-64ae216c492d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d2163610d1ea537301ec61e1a34c8b6e727d6e0
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85759454"
---
# <a name="type-system---sequence-type-matching"></a>형식 시스템 - 시퀀스 형식 일치
[!INCLUDE [SQL Server Azure SQL Database ](../includes/applies-to-version/sqlserver.md)]

  XQuery 식 값은 항상 0개 이상의 항목에 대한 시퀀스입니다. 항목은 원자 값이거나 노드일 수 있습니다. 시퀀스 유형은 쿼리 식에 의해 반환된 시퀀스 유형을 특정 유형과 일치하는지 검색하는 기능을 참조합니다. 예를 들면 다음과 같습니다.  
  
-   식의 값이 원자 값인 경우 값이 integer, decimal 또는 string 유형인지 여부를 확인할 수 있습니다.  
  
-   식의 값이 XML 노드인 경우 값이 주석 노드, 처리 명령 노드 또는 텍스트 노드인지 여부를 확인할 수 있습니다.  
  
-   식이 XML 요소나 특정 이름 및 유형의 특성 노드를 반환하는지 여부를 확인할 수 있습니다.  
  
 시퀀스 유형 일치에서는 `instance of` 부울 연산자를 사용할 수 있습니다. 식에 대 한 자세한 내용은 `instance of` [SequenceType Expressions &#40;XQuery&#41;](../xquery/sequencetype-expressions-xquery.md)를 참조 하세요.  
  
## <a name="comparing-the-atomic-value-type-returned-by-an-expression"></a>식에 의해 반환된 원자 값 유형 비교  
 식이 원자 값 시퀀스를 반환하는 경우 시퀀스에서 값의 유형을 찾아야 할 수도 있습니다. 다음 예에서는 시퀀스 유형 구문을 사용하여 식에 의해 반환된 원자 값 유형을 평가하는 방법을 보여 줍니다.  
  
### <a name="example-determining-whether-a-sequence-is-empty"></a>예: 시퀀스가 비어 있는지 확인  
 **빈 ()** 시퀀스 형식은 시퀀스 형식 식에 사용 하 여 지정 된 식에서 반환 된 시퀀스가 빈 시퀀스 인지 여부를 확인할 수 있습니다.  
  
 다음 예에서는 XML 스키마를 사용 하 여 <`root`> 요소를 nillable 수 있습니다.  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
      <element name="root" nillable="true" type="byte"/>  
</schema>'  
GO  
```  
  
 이제 형식화 된 XML 인스턴스가 <> 요소에 대 한 값을 지정 하는 경우 `root` 는 `instance of empty()` False를 반환 합니다.  
  
```  
DECLARE @var XML(SC1)  
SET @var = '<root>1</root>'  
-- The following returns False  
SELECT @var.query('data(/root[1]) instance of  empty() ')  
GO  
```  
  
 `root`인스턴스에 <> 요소가 nillable 경우 해당 값은 빈 시퀀스이 고는 `instance of empty()` True를 반환 합니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" />'  
SELECT @var.query('data(/root[1]) instance of  empty() ')  
GO  
```  
  
### <a name="example-determining-the-type-of-an-attribute-value"></a>예: 특성 값의 형식 확인  
 일부 경우에는 처리 전에 식에 의해 반환된 시퀀스 유형을 평가해야 할 수 있습니다. 예를 들어 노드가 UNION 유형으로 정의된 XML 스키마가 있을 수 있습니다. 다음 예에서 컬렉션에 있는 XML 스키마는 값이 decimal이나 string 유형일 수 있는 특성 `a`를 UNION 유형으로 정의합니다.  
  
```  
-- Drop schema collection if it exists.  
-- DROP XML SCHEMA COLLECTION SC.  
-- GO  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
  <element name="root">  
    <complexType>  
       <sequence/>  
         <attribute name="a">  
            <simpleType>  
               <union memberTypes="decimal string"/>  
            </simpleType>  
         </attribute>  
     </complexType>  
  </element>  
</schema>'  
GO  
```  
  
 형식화된 XML 인스턴스를 처리하기 전에 특성 `a` 값의 유형을 알아야 할 수 있습니다. 다음 예에서 특성 `a` 값의 유형은 decimal입니다. 따라서 `, instance of xs:decimal` True를 반환 합니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root a="2.5"/>'  
SELECT @var.query('data((/root/@a)[1]) instance of xs:decimal')  
GO  
```  
  
 이제 특성 `a` 값을 string 유형으로 바꿉니다. 그러면 `instance of xs:string`은 True를 반환합니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root a="Hello"/>'  
SELECT @var.query('data((/root/@a)[1]) instance of xs:string')  
GO  
```  
  
### <a name="example-cardinality-in-sequence-expressions"></a>예: 시퀀스 식의 카디널리티  
 이 예에서는 시퀀스 식의 카디널리티 효과를 보여 줍니다. 다음 XML 스키마는 `root` 바이트 유형이 며 nillable 인 <> 요소를 정의 합니다.  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
      <element name="root" nillable="true" type="byte"/>  
</schema>'  
GO  
```  
  
 다음 쿼리에서 식은 바이트 유형의 단일 항목을 반환하기 때문에 `instance of`는 True를 반환합니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root>111</root>'  
SELECT @var.query('data(/root[1]) instance of  xs:byte ')   
GO  
```  
  
 <`root`> 요소 nil로 설정 하면 해당 값은 빈 시퀀스입니다. 즉, `/root[1]` 식은 빈 시퀀스를 반환합니다. 따라서 `instance of xs:byte`는 False를 반환합니다. 이 경우의 기본 카디널리티는 1입니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"></root>'  
SELECT @var.query('data(/root[1]) instance of  xs:byte ')   
GO  
-- result = false  
```  
  
 발생 표시(`?`)를 추가하여 카디널리티를 지정하는 경우 시퀀스 식은 True를 반환합니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"></root>'  
SELECT @var.query('data(/root[1]) instance of  xs:byte? ')   
GO  
-- result = true  
```  
  
 시퀀스 유형의 식에서 테스트는 다음 두 가지 단계로 완료됩니다.  
  
1.  첫 번째, 테스트는 식 유형이 지정된 유형과 일치하는지 여부를 확인합니다.  
  
2.  일치하면 테스트는 식에 의해 반환된 항목 개수가 지정된 발생 표시와 일치하는지 여부를 결정합니다.  
  
 두 값이 모두 True인 경우 `instance of` 식은 True를 반환합니다.  
  
### <a name="example-querying-against-an-xml-type-column"></a>예: xml 유형 열에 대 한 쿼리  
 다음 예에서는 데이터베이스에 있는 **xml** 유형의 명령 열에 대해 쿼리를 지정 합니다 [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] . 이 열은 연결된 스키마가 포함되므로 형식화된 XML 열입니다. XML 스키마는 정수 유형의 `LocationID` 특성을 정의합니다. 따라서 시퀀스 식에서는 `instance of xs:integer?` True를 반환 합니다.  
  
```  
SELECT Instructions.query('   
declare namespace AWMI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";   
data(/AWMI:root[1]/AWMI:Location[1]/@LocationID) instance of xs:integer?') as Result   
FROM Production.ProductModel   
WHERE ProductModelID = 7  
```  
  
## <a name="comparing-the-node-type-returned-by-an-expression"></a>식에 의해 반환되는 노드 유형 비교  
 식이 노드의 시퀀스를 반환하는 경우 시퀀스에서 노드의 유형을 찾아야 할 수 있습니다. 다음 예에서는 시퀀스 유형 구문을 사용하여 식에 의해 반환된 노드 유형을 평가하는 방법을 보여 줍니다. 사용할 수 있는 시퀀스 유형은 다음과 같습니다.  
  
-   **item ()** -시퀀스의 모든 항목을 찾습니다.  
  
-   **node ()** -시퀀스가 노드인지 여부를 확인 합니다.  
  
-   **processing-명령 ()** -식이 처리 명령을 반환 하는지 여부를 확인 합니다.  
  
-   **comment ()** -식이 주석을 반환 하는지 여부를 확인 합니다.  
  
-   **document-node ()** -식이 문서 노드를 반환 하는지 여부를 확인 합니다.  
  
 다음 예에서는 이러한 시퀀스 유형을 보여 줍니다.  
  
### <a name="example-using-sequence-types"></a>예: 시퀀스 형식 사용  
 이 예에서 일부 쿼리는 형식화되지 않은 XML 변수에 대해 실행됩니다. 다음 쿼리에서는 시퀀스 유형을 사용하는 방법을 보여 줍니다.  
  
```  
DECLARE @var XML  
SET @var = '<?xml-stylesheet href="someValue" type="text/xsl" ?>  
<root>text node  
  <!-- comment 1 -->   
  <a>Data a</a>  
  <!-- comment  2 -->  
</root>'  
```  
  
 첫 번째 쿼리에서 식은 <> 요소의 형식화 된 값을 반환 합니다 `a` . 두 번째 쿼리에서 식은 요소 <`a`> 반환 합니다. 두 개 모두 항목입니다. 따라서 두 쿼리는 모두 True를 반환합니다.  
  
```  
SELECT @var.query('data(/root[1]/a[1]) instance of item()')  
SELECT @var.query('/root[1]/a[1] instance of item()')  
```  
  
 다음 세 쿼리의 모든 XQuery 식은 <> 요소의 요소 노드 자식을 반환 합니다 `root` . 따라서 시퀀스 유형의 식인 `instance of node()`는 True를 반환하고 다른 두 개의 식인 `instance of text()` 및 `instance of document-node()`는 False를 반환합니다.  
  
```  
SELECT @var.query('(/root/*)[1] instance of node()')  
SELECT @var.query('(/root/*)[1] instance of text()')  
SELECT @var.query('(/root/*)[1] instance of document-node()')   
```  
  
 다음 쿼리에서 `instance of document-node()` 식은 <`root`> 요소의 부모가 문서 노드인지 때문에 True를 반환 합니다.  
  
```  
SELECT @var.query('(/root/..)[1] instance of document-node()') -- true  
```  
  
 다음 쿼리에서 식은 XML 인스턴스에서 첫 번째 노드를 검색합니다. 이 노드는 처리 명령 노드이기 때문에 `instance of processing-instruction()` 식은 True를 반환합니다.  
  
```  
SELECT @var.query('(/node())[1] instance of processing-instruction()')  
```  
  
### <a name="implementation-limitations"></a>구현 시 제한 사항  
 특정 제한 사항은 다음과 같습니다.  
  
-   콘텐츠 형식 구문이 있는 **문서-노드 ()** 는 지원 되지 않습니다.  
  
-   **처리 명령 (name)** 구문은 지원 되지 않습니다.  
  
## <a name="element-tests"></a>요소 테스트  
 요소 테스트는 식에 의해 반환된 요소 노드가 특정 이름 및 유형의 요소 노드와 일치하는지 확인하기 위해 사용됩니다. 사용할 수 있는 요소 테스트는 다음과 같습니다.  
  
```  
element ()  
element(ElementName)  
element(ElementName, ElementType?)   
element(*, ElementType?)  
```  
  
## <a name="attribute-tests"></a>특성 테스트  
 특성 테스트는 식에 의해 반환된 특성이 특성 노드인지 여부를 확인합니다. 사용할 수 있는 특성 테스트는 다음과 같습니다.  
  
 `attribute()`  
  
 `attribute(AttributeName)`  
  
 `attribute(AttributeName, AttributeType)`  
  
## <a name="test-examples"></a>테스트 예  
 다음 예에서는 요소 테스트 및 특성 테스트를 유용하게 사용할 수 있는 시나리오를 보여 줍니다.  
  
### <a name="example-a"></a>예 1  
 다음 XML 스키마는 `CustomerType` <`firstName`> 및 <`lastName`> 요소가 선택적인 복합 유형을 정의 합니다. 지정된 XML 인스턴스에서 특정 고객의 이름이 있는지 여부를 확인해야 할 수 있습니다.  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
targetNamespace="myNS" xmlns:ns="myNS">  
  <complexType name="CustomerType">  
     <sequence>  
        <element name="firstName" type="string" minOccurs="0"   
                  nillable="true" />  
        <element name="lastName" type="string" minOccurs="0"/>  
     </sequence>  
  </complexType>  
  <element name="customer" type="ns:CustomerType"/>  
</schema>  
'  
GO  
DECLARE @var XML(SC)  
SET @var = '<x:customer xmlns:x="myNS">  
<firstName>SomeFirstName</firstName>  
<lastName>SomeLastName</lastName>  
</x:customer>'  
```  
  
 다음 쿼리에서는 식을 사용 하 여 `instance of element (firstName)` <>의 첫 번째 자식 요소가 `customer` 이름이 <> 요소 인지 여부를 확인 `firstName` 합니다. 이 경우에는 True가 반환됩니다.  
  
```  
SELECT @var.query('declare namespace x="myNS";   
     (/x:customer/*)[1] instance of element (firstName)')  
GO  
```  
  
 인스턴스에서 <> 요소를 제거 하면 `firstName` 쿼리가 False를 반환 합니다.  
  
 다음 구문을 사용할 수도 있습니다.  
  
-   다음 쿼리에 표시된 `element(ElementName, ElementType?)` 시퀀스 유형 구문. 이 구문은 이름이 `firstName`이고 유형이 `xs:string`인 nillable 또는 비-nillable 요소 노드가 일치하는지 검색합니다.  
  
    ```  
    SELECT @var.query('declare namespace x="myNS";   
    (/x:customer/*)[1] instance of element (firstName, xs:string?)')  
    ```  
  
-   다음 쿼리에 표시된 `element(*, type?)` 시퀀스 유형 구문. 이 구문은 해당 유형이 `xs:string`인 경우 이름에 관계없이 요소 노드가 일치하는지 검색합니다.  
  
    ```  
    SELECT @var.query('declare namespace x="myNS"; (/x:customer/*)[1] instance of element (*, xs:string?)')  
    GO  
    ```  
  
### <a name="example-b"></a>예 2  
 다음 예에서는 식에 의해 반환된 노드가 특정 이름의 요소 노드인지 여부를 확인하는 방법을 보여 줍니다. **요소 ()** 테스트를 사용 합니다.  
  
 다음 예제에서 `Customer` 쿼리 중인 XML 인스턴스의 두 <> 요소는 두 가지 유형 `CustomerType` 및 `SpecialCustomerType` 입니다. 식에서 반환 하는 <> 요소의 형식을 알고 있다고 가정 합니다 `Customer` . 다음 XML 스키마 컬렉션은 `CustomerType` 및 `SpecialCustomerType` 유형을 정의합니다.  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
          targetNamespace="myNS"  xmlns:ns="myNS">  
  <complexType name="CustomerType">  
    <sequence>  
      <element name="firstName" type="string"/>  
      <element name="lastName" type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="SpecialCustomerType">  
     <complexContent>  
       <extension base="ns:CustomerType">  
        <sequence>  
            <element name="Age" type="int"/>  
        </sequence>  
       </extension>  
     </complexContent>  
    </complexType>  
   <element name="customer" type="ns:CustomerType"/>  
</schema>  
'  
GO  
```  
  
 이 XML 스키마 컬렉션은 형식화 된 **xml** 변수를 만드는 데 사용 됩니다. 이 변수에 할당 된 XML 인스턴스에는 두 개의 `customer` 서로 다른 형식에 대 한 두 개의 <> 요소가 있습니다. 첫 번째 요소는 `CustomerType` 유형이며 두 번째 요소는 `SpecialCustomerType` 유형입니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '  
<x:customer xmlns:x="myNS">  
   <firstName>FirstName1</firstName>  
   <lastName>LastName1</lastName>  
</x:customer>  
<x:customer xsi:type="x:SpecialCustomerType" xmlns:x="myNS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <firstName> FirstName2</firstName>  
   <lastName> LastName2</lastName>  
   <Age>21</Age>  
</x:customer>'  
```  
  
 다음 쿼리에서 `instance of element (*, x:SpecialCustomerType ?)` 식은 `SpecialCustomerType` 유형이 아닌 첫 번째 고객 요소를 반환하기 때문에 False를 반환합니다.  
  
```  
SELECT @var.query('declare namespace x="myNS";   
    (/x:customer)[1] instance of element (*, x:SpecialCustomerType ?)')  
```  
  
 이전 쿼리의 식을 변경 하 고 두 번째 <> 요소 ()를 검색 하는 경우 `customer` `/x:customer)[2]` 는 `instance of` True를 반환 합니다.  
  
### <a name="example-c"></a>예 3  
 이 예에서는 특성 테스트가 사용됩니다. 다음 XML 스키마는 CustomerID 및 Age 특성이 포함된 CustomerType 복합 유형을 정의합니다. Age 특성은 선택 사항입니다. 특정 XML 인스턴스의 경우 <> 요소에 Age 특성이 있는지 여부를 확인 하는 것이 좋습니다 `customer` .  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
       targetNamespace="myNS" xmlns:ns="myNS">  
<complexType name="CustomerType">  
  <sequence>  
     <element name="firstName" type="string" minOccurs="0"   
               nillable="true" />  
     <element name="lastName" type="string" minOccurs="0"/>  
  </sequence>  
  <attribute name="CustomerID" type="integer" use="required" />  
  <attribute name="Age" type="integer" use="optional" />  
 </complexType>  
 <element name="customer" type="ns:CustomerType"/>  
</schema>  
'  
GO  
```  
  
 다음 쿼리는 쿼리되는 XML 인스턴스에 이름이 `Age`인 특성 노드가 있기 때문에 True를 반환합니다. 이 식에서는 `attribute(Age)` 특성 테스트가 사용됩니다. 특성에 순서가 없기 때문에 이 쿼리에서는 FLWOR 식을 사용하여 모든 특성을 검색한 다음 `instance of` 식을 사용하여 각 특성을 테스트합니다. 이 예에서는 먼저 XML 스키마 컬렉션을 만들어 형식화 된 **xml** 변수를 만듭니다.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<x:customer xmlns:x="myNS" CustomerID="1" Age="22" >  
<firstName>SomeFName</firstName>  
<lastName>SomeLName</lastName>  
</x:customer>'  
SELECT @var.query('declare namespace x="myNS";   
FOR $i in /x:customer/@*  
RETURN  
    IF ($i instance of attribute (Age)) THEN  
        "true"  
        ELSE  
        ()')     
GO  
  
```  
  
 인스턴스에서 선택 사항인 `Age` 특성을 제거하면 이전 쿼리가 False를 반환합니다.  
  
 특성 테스트에서 특성 이름 및 유형(`attribute(name,type)`)을 지정할 수 있습니다.  
  
```  
SELECT @var.query('declare namespace x="myNS";   
FOR $i in /x:customer/@*  
RETURN  
    IF ($i instance of attribute (Age, xs:integer)) THEN  
        "true"  
        ELSE  
        ()')  
```  
  
 또는 `attribute(*, type)` 시퀀스 유형 구문을 지정할 수 있습니다. 이렇게 하면 특성 유형이 지정된 유형과 일치하는 경우 이름에 관계없이 특성 노드가 일치하는지 검색합니다.  
  
### <a name="implementation-limitations"></a>구현 시 제한 사항  
 특정 제한 사항은 다음과 같습니다.  
  
-   요소 테스트에서 형식 이름 뒤에는 발생 표시기 (**?**)가와 야 합니다.  
  
-   **요소 (ElementName, TypeName)** 는 지원 되지 않습니다.  
  
-   **요소 ( \* , TypeName)** 는 지원 되지 않습니다.  
  
-   **스키마 요소 ()** 는 지원 되지 않습니다.  
  
-   **스키마 특성 (AttributeName)** 은 지원 되지 않습니다.  
  
-   **Xsi: type** 또는 **xsi: nil** 을 명시적으로 쿼리 하는 것은 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Type System &#40;XQuery&#41;](../xquery/type-system-xquery.md)  
  
  
