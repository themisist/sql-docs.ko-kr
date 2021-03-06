---
title: 간격 이스케이프 시퀀스 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- interval literals [ODBC]
- escape sequences [ODBC], interval
- ODBC escape sequences [ODBC], interval
ms.assetid: 303e8dab-8f13-4fa5-857f-15cc1f75bdd6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9fe7f6941e9ec9fba8b6698faaa18a678732dd6f
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304958"
---
# <a name="interval-escape-sequences"></a>간격 이스케이프 시퀀스
ODBC에서는 간격 리터럴에 이스케이프 시퀀스를 사용 합니다. 이 이스케이프 시퀀스의 구문은 다음과 같습니다.  
  
 {*interval-literal*}  
  
 *Interval 리터럴의*BNF 구문에 대해서는이 부록 뒷부분의 [interval 리터럴 구문](../../../odbc/reference/appendixes/interval-literal-syntax.md) 단원을 참조 하세요.  
  
 간격 리터럴 이스케이프 시퀀스는 데이터 원본에서 간격 데이터 형식이 지원 되는 경우에만 지원 됩니다. 응용 프로그램은 **SQLGetTypeInfo** 를 호출 하 여 이러한 데이터 형식이 지원 되는지 여부를 확인 해야 합니다.
