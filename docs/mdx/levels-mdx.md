---
title: 수준 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 24e15602593f9116d499345ffca093f86ecfa135
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2020
ms.locfileid: "67905641"
---
# <a name="levels-mdx"></a>Levels(MDX)


  차원 또는 계층에서의 위치가 숫자 식에 의해 지정되거나 이름이 문자열 식에 의해 지정되는 수준을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Numeric expression syntax  
Hierarchy_Expression.Levels( Level_Number )  
  
String expression syntax  
Hierarchy_Expression.Levels( Level_Name )  
```  
  
## <a name="arguments"></a>인수  
 *Hierarchy_Expression*  
 계층을 반환하는 유효한 MDX 식입니다.  
  
 *Level_Number*  
 수준 번호를 지정하는 유효한 숫자 식입니다.  
  
 *Level_Name*  
 수준 이름을 지정하는 유효한 문자열 식입니다.  
  
## <a name="remarks"></a>설명  
 수준 번호가 지정 된 경우 수준 함수는 지정 된 위치 (0부터 시작)와 관련 된 수준을 **반환 합니다.**  
  
 수준 이름이 지정 된 경우 수준 함수는 지정 된 수준을 **반환 합니다.**  
  
> [!NOTE]  
>  사용자 정의 함수에 대해서는 문자열 식 구문을 사용합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 각 **수준의** 함수 구문을 보여 줍니다.  
  
### <a name="numeric"></a>숫자  
 다음 예에서는 Country 수준을 반환합니다.  
  
```  
SELECT [Geography].[Geography].Levels(1) ON 0  
FROM [Adventure Works]  
```  
  
### <a name="string"></a>String  
 다음 예에서는 Country 수준을 반환합니다.  
  
```  
SELECT [Geography].[Geography].Levels('Country') ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
