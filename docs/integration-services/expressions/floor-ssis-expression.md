---
title: FLOOR(SSIS 식) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f0161fe842ad8271d04a69b9cb2726db3403314
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86917016"
---
# <a name="floor-ssis-expression"></a>FLOOR(SSIS 식)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  숫자 식보다 작거나 같은 최대 정수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a>인수  
 *numeric_expression*  
 유효한 숫자 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 인수 식의 숫자 데이터 형식입니다. 결과는 *numeric_expression*과 동일한 데이터 형식으로 계산된 값의 정수 부분입니다.  
  
## <a name="remarks"></a>설명  
 인수가 Null이면 FLOOR 결과도 Null입니다.  
  
## <a name="expression-examples"></a>식 예  
 이 예에서는 FLOOR 함수를 양수, 음수 및 0 값에 적용합니다.  
  
```  
FLOOR(123.45)  
```  
  
 123.00을 반환합니다.  
  
```  
FLOOR(-123.45)  
```  
  
 -124.00을 반환합니다.  
  
```  
FLOOR(0.00)  
```  
  
 0\.00을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CEILING&#40;SSIS 식&#41;](../../integration-services/expressions/ceiling-ssis-expression.md)   
 [함수&#40;SSIS 식&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
