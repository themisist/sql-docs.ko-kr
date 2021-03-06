---
title: Hierarchize (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 8ab2c866f201c53684c316282a143b4f672cb8e9
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68105430"
---
# <a name="hierarchize-mdx"></a>Hierarchize(MDX)


  집합의 멤버를 계층 구조 형태로 정렬합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Hierarchize(Set_Expression [ , POST ] )  
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>설명  
 **Hierarchize** 함수는 지정 된 집합의 멤버를 계층적 순서로 구성 합니다. 함수는 항상 중복 요소를 포함합니다.  
  
-   **POST** 를 지정 하지 않으면 함수는 수준에서 멤버를 자연 순서로 정렬 합니다. 일반적인 방향의 순서는 다른 정렬 조건이 지정되지 않은 경우 계층에서 멤버가 정렬되는 기본 순서입니다. 자식 멤버는 해당 부모 멤버 바로 다음에 옵니다.  
  
-   **Post** 를 지정 하면 **Hierarchize** 함수는 일반 순서를 사용 하 여 수준에서 멤버를 정렬 합니다. 즉, 자식 멤버가 해당 부모보다 앞에 옵니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 Canada 멤버를 드릴업합니다. **Hierarchize** 함수는 지정 된 집합 멤버를 계층 순서로 구성 하는 데 사용 됩니다 .이는 **DrillUpMember** 함수에 필요 합니다.  
  
```  
SELECT DrillUpMember   
   (  
      Hierarchize  
         (  
            {[Geography].[Geography].[Country].[Canada]  
            ,[Geography].[Geography].[Country].[United States]  
            ,[Geography].[Geography].[State-Province].[Alberta]  
            ,[Geography].[Geography].[State-Province].[Brunswick]  
            ,[Geography].[Geography].[State-Province].[Colorado]   
            }  
         ), {[Geography].[Geography].[Country].[United States]}  
   )  
ON 0  
FROM [Adventure Works]  
```  
  
 다음 예에서는 **놀이 Works** 큐브에서 `Date` 차원에 `Measures.[Order Quantity]` 포함 된 2003의 처음 9 개월 동안 집계 된 멤버의 합계를 반환 합니다. **PeriodsToDate** 함수는 집계 함수가 작동 하는 집합의 튜플을 정의 합니다. **Hierarchize** 함수는 Product 차원의 지정 된 멤버 집합의 멤버를 계층적 순서로 구성 합니다.  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS Count  
   (Filter  
      (Existing  
         (Reseller.Reseller.Reseller),   
            [Measures].[Reseller Sales Amount] <   
               ([Measures].[Reseller Sales Amount],[Date].Calendar.PrevMember)  
        )  
    )  
MEMBER [Geography].[State-Province].x AS Aggregate   
( {[Geography].[State-Province].&[WA]&[US],   
   [Geography].[State-Province].&[OR]&[US] }   
)  
SELECT NON EMPTY HIERARCHIZE   
   (AddCalculatedMembers   
      ({DrillDownLevel  
         ({[Product].[All Products]})}  
        )  
    ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE ([Geography].[State-Province].x,   
   [Date].[Calendar].[Calendar Quarter].&[2003]&[4],  
   [Measures].[Declining Reseller Sales])  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
