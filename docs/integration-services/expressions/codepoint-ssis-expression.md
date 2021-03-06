---
title: CODEPOINT(SSIS 식) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e856482cd7ef4094b6383d6365efe88d83c84bb0
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916453"
---
# <a name="codepoint-ssis-expression"></a>CODEPOINT(SSIS 식)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  문자 식에서 가장 왼쪽 문자의 유니코드 코드 포인트를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a>인수  
 *character_expression*  
 가장 왼쪽의 문자를 평가할 문자 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 DT_UI2  
  
## <a name="remarks"></a>설명  
 *character_expression* 인수는 DT_WSTR 데이터 형식이어야 합니다.  
  
 *character_expression* 이 Null이거나 빈 문자열이면 CODEPOINT 결과도 Null이 됩니다.  
  
## <a name="expression-examples"></a>식 예  
 이 예에서는 문자열 리터럴을 사용합니다. 반환 결과는 M의 유니코드 코드 포인트인 77입니다.  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 이 예에서는 변수를 사용합니다. **Name** 이 Touring Front Wheel이면 반환 결과는 T의 유니코드 코드 포인트인 84입니다.  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a>참고 항목  
 [함수&#40;SSIS 식&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
