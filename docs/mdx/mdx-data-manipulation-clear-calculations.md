---
title: CLEAR 계산 문 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 1b0766cb002960a96d702184ac9719abe7610afd
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "67938028"
---
# <a name="mdx-data-manipulation---clear-calculations"></a>MDX 데이터 조작 - CLEAR CALCULATIONS


  큐브에서 모든 계산을 제거하고 큐브를 계산 패스 0으로 되돌립니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
CLEAR CALCULATIONS [FROMCube_Expression]  
```  
  
## <a name="arguments"></a>인수  
 *Cube_Expression*  
 유효한 MDX 큐브 식입니다.  
  
## <a name="remarks"></a>설명  
 MDX 스크립트 에서처럼 **FROM** 절은 큐브의 컨텍스트를 알 수 없는 경우 생략 될 수 있습니다.  
  
> [!NOTE]  
>  이 문은 서버 또는 데이터베이스 관리자나 큐브의 원본 데이터에 액세스할 수 있는 역할(즉, ReadSourceData=true인 역할)의 멤버만 실행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Mdx 데이터 조작 문은 MDX를 &#40;&#41;](../mdx/mdx-data-manipulation-statements-mdx.md)  
  
  
