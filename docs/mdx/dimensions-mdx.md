---
title: 차원 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 84d5ab0caa22c6f35f3e7b790dbfb3348df8ceb1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "67999970"
---
# <a name="dimensions-mdx"></a>Dimensions(MDX)


  숫자 식 또는 문자열 식으로 지정된 계층을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Numeric expression syntax  
Dimensions(Hierarchy_Number)  
  
String expression syntax  
Dimensions(Hierarchy_Name)  
```  
  
## <a name="arguments"></a>인수  
 *Hierarchy_Number*  
 계층 번호를 지정하는 유효한 숫자 식입니다.  
  
 *Hierarchy_Name*  
 계층 이름을 지정하는 유효한 문자열 식입니다.  
  
## <a name="remarks"></a>설명  
 계층 번호가 지정 된 경우 **차원** 함수는 큐브 내의 위치 (0부터 시작)가 지정 된 계층 번호를 가진 계층을 반환 합니다.  
  
 계층 이름이 지정 된 경우 **차원** 함수는 지정 된 계층을 반환 합니다. 일반적으로 사용자 정의 함수를 사용 하 여이 문자열 버전의 **차원** 함수를 사용 합니다.  
  
> [!NOTE]  
>  **측정값** 차원은 항상로 `Dimensions(0)`표시 됩니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 **차원** 함수를 사용 하 여 숫자 식과 문자열 식을 모두 사용 하 여 지정 된 계층의 이름, 수준 수 및 멤버 수를 반환 합니다.  
  
```  
WITH MEMBER Measures.x AS Dimensions  
   ('[Product].[Product Model Lines]').Name  
SELECT Measures.x on 0  
FROM [Adventure Works]  
  
WITH MEMBER Measures.x AS Dimensions  
   ('[Product].[Product Model Lines]').Levels.Count  
SELECT Measures.x on 0  
FROM [Adventure Works]  
  
WITH MEMBER Measures.x AS Dimensions  
   ('[Product].[Product Model Lines]').Members.Count  
SELECT Measures.x on 0  
FROM [Adventure Works]  
  
WITH MEMBER Measures.x AS Dimensions(0).Name  
SELECT Measures.x on 0  
FROM [Adventure Works]  
  
WITH MEMBER Measures.x AS Dimensions(0).Levels.Count  
SELECT measures.x on 0  
FROM [Adventure Works]  
  
WITH MEMBER Measures.x AS Dimensions(0).Members.Count  
SELECT measures.x on 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
