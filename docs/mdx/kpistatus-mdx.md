---
title: KPIStatus (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: aa07788bc00cc3317024d287f1054a67c6447356
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2020
ms.locfileid: "67905879"
---
# <a name="kpistatus-mdx"></a>KPIStatus(MDX)


  지정된 KPI(핵심 성과 지표)의 상태 부분을 나타내는 정규화된 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
KPIStatus(KPI_Name)  
```  
  
## <a name="arguments"></a>인수  
 *KPI_Name*  
 KPI의 이름을 지정하는 유효한 문자열 식입니다.  
  
## <a name="remarks"></a>설명  
 상태 값은 일반적으로 -1에서 1 사이의 정규화된 값입니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 Fiscal Year 특성 계층 중 세 멤버의 하위 항목에 대한 채널 수익 측정값의 KPI 값, KPI 목표, KPI 상태 및 KPI 추세를 반환합니다.  
  
```  
SELECT  
   { KPIValue("Channel Revenue"),   
     KPIGoal("Channel Revenue"),  
     KPIStatus("Channel Revenue"),   
     KPITrend("Channel Revenue")  
   } ON Columns,  
Descendants  
   ( { [Date].[Fiscal].[Fiscal Year].&[2002],  
       [Date].[Fiscal].[Fiscal Year].&[2003],  
       [Date].[Fiscal].[Fiscal Year].&[2004]   
     }, [Date].[Fiscal].[Fiscal Quarter]  
   ) ON Rows  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
