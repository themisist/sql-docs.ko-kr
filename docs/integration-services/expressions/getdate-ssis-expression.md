---
title: GETDATE(SSIS 식) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 36646e7411312cd6285f61dafbb64628bb82eb20
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916997"
---
# <a name="getdate-ssis-expression"></a>GETDATE(SSIS 식)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  시스템의 현재 날짜를 DT_DBTIMESTAMP 형식으로 반환합니다. GETDATE 함수는 인수가 필요 없습니다.  
  
> [!NOTE]  
>  GETDATE 함수의 반환 결과 길이는 29자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a>인수  
 None  
  
## <a name="result-types"></a>결과 형식  
 DT_DBTIMESTAMP  
  
## <a name="expression-examples"></a>식 예  
 이 예에서는 현재 날짜의 연도를 반환합니다.  
  
```  
DATEPART("year",GETDATE())  
```  
  
 이 예에서는 **ModifiedDate** 열의 날짜와 현재 날짜 사이의 일 수를 반환합니다.  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 이 예에서는 현재 날짜에 3개월을 더합니다.  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a>참고 항목  
 [GETUTCDATE&#40;SSIS 식&#41;](../../integration-services/expressions/getutcdate-ssis-expression.md)   
 [함수&#40;SSIS 식&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
