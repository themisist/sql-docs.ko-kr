---
title: FREEZE 문 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 4738dab411fe55808034a6d9d81a16994089ea74
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68138293"
---
# <a name="mdx-scripting---freeze"></a>MDX 스크립팅 - FREEZE


  지정한 하위 큐브의 셀 값을 현재 값으로 잠급니다. 셀 값이 잠기면 이 셀은 다른 셀이 변경되어도 영향을 받지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
FREEZE Subcube_Expression   
```  
  
## <a name="arguments"></a>인수  
 *Subcube_Expression*  
 하위 큐브를 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>설명  
 **고정** 문은 지정 된 하위 큐브에서 셀 값을 잠가서 후속 계산 패스에서 MDX 스크립트의 이후 문이 해당 값을 변경 하지 못하도록 방지 합니다.  
  
 다음 예에서 A와 B는 MDX 계산 스크립트의 하위 큐브를 나타냅니다.  
  
```  
B = 2;  
A = B;  
B = 3  
```  
  
 여기서 A와 B 모두 3과 같습니다.  
  
 이제 **고정** 함수를 삽입 하 여 A 하위 큐브의 셀을 잠급니다.  
  
```  
B = 2;  
A = B;  
FREEZE(A);  
B = 3  
```  
  
 그러면 A는 2가 되고 B는 3이 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDX 스크립팅 문&#40;MDX&#41;](../mdx/mdx-scripting-statements-mdx.md)  
  
  
