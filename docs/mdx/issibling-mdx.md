---
title: IsSibling (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 15c80cec67b0a40c8ac4c436a45a4551132858f1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68105356"
---
# <a name="issibling-mdx"></a>IsSibling(MDX)


  지정한 멤버가 지정한 다른 멤버의 형제 항목인지 여부를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
IsSibling(Member_Expression1, Member_Expression2)   
```  
  
## <a name="arguments"></a>인수  
 *Member_Expression1*  
 멤버를 반환하는 유효한 MDX 식입니다.  
  
 *Member_Expression2*  
 멤버를 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>설명  
 **Issibling** 함수는 지정 된 첫 번째 멤버가 지정 된 두 번째 멤버의 형제 인 경우 **true** 를 반환 합니다. 그렇지 않으면 함수는 **false**를 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 Date 차원의 Fiscal 계층에 있는 현재 멤버가 2002년 7월의 형제인 경우 TRUE를 반환합니다.  
  
 `WITH MEMBER MEASURES.ISSIBLINGDEMO AS`  
  
 `IsSibling([Date].[Fiscal].CURRENTMEMBER, [Date].[Fiscal].[Month].&[2002]&[7])`  
  
 `SELECT {MEASURES.ISSIBLINGDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
