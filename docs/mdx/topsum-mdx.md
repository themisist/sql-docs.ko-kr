---
title: TopSum (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 5bbcfe52e62757ea00427eb9fd6ed979eb8d32e7
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68097395"
---
# <a name="topsum-mdx"></a>TopSum(MDX)


  집합을 정렬하고 누적 합계가 지정한 값 이상이 되는 상위 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
TopSum(Set_Expression, Value, Numeric_Expression)   
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
 *값*  
 각 튜플과 비교할 기준 값을 지정하는 유효한 숫자 식입니다.  
  
 *Numeric_Expression*  
 측정값을 반환하는 유효한 숫자 식으로서, 일반적으로 MDX 식입니다.  
  
## <a name="remarks"></a>설명  
 **TopSum** 함수는 지정 된 집합에 대해 계산 된 지정 된 측정값의 합계를 계산 하 여 집합을 내림차순으로 정렬 합니다. 그런 다음 지정된 숫자 식의 합계가 지정된 값(합계) 이상이 되는 상위 값 요소를 반환합니다. 이 함수는 누적 합계가 지정된 값 이상이 되는 집합의 가장 작은 하위 집합을 반환합니다. 반환되는 요소는 가장 큰 값에서 가장 작은 값 순서로 정렬됩니다.  
  
> [!IMPORTANT]  
>  [BottomSum](../mdx/bottomsum-mdx.md) 함수와 마찬가지로 **TopSum** 함수는 항상 계층 구조를 중단 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 Bike 범주에 대해 Geography 차원의 Geography 계층에 있는 City 수준의 멤버 중에서 Reseller Sales Amount 측정값을 사용한 누적 합계가 6,000,000 이상인 멤버의 최소 집합을 판매량이 가장 많은 멤버부터 반환합니다.  
  
```  
SELECT [Measures].[Reseller Sales Amount] ON 0,  
TopSum  
   ({[Geography].[Geography].[City].Members}  
   , 6000000  
   , [Measures].[Reseller Sales Amount]  
   ) ON 1  
FROM [Adventure Works]  
WHERE([Product].[Product Categories].Bikes)  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
