---
title: 분석 함수(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 60fbff84-673b-48ea-9254-6ecdad20e7fe
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: fcb02ea9ba7b93c606bb6fa00fd8547fc0ef376b
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396982"
---
# <a name="analytic-functions-transact-sql"></a>분석 함수(Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

SQL Server는 다음과 같은 분석 함수를 지원합니다.

- [CUME_DIST&#40;Transact-SQL&#41;](../../t-sql/functions/cume-dist-transact-sql.md)
- [FIRST_VALUE&#40;Transact-SQL&#41;](../../t-sql/functions/first-value-transact-sql.md)
- [LAG&#40;Transact-SQL&#41;](../../t-sql/functions/lag-transact-sql.md)
- [LAST_VALUE&#40;Transact-SQL&#41;](../../t-sql/functions/last-value-transact-sql.md)
- [LEAD&#40;Transact-SQL&#41;](../../t-sql/functions/lead-transact-sql.md)
- [PERCENT_RANK&#40;Transact-SQL&#41;](../../t-sql/functions/percent-rank-transact-sql.md)
- [PERCENTILE_CONT&#40;Transact-SQL&#41;](../../t-sql/functions/percentile-cont-transact-sql.md)  
- [PERCENTILE_DISC&#40;Transact-SQL&#41;](../../t-sql/functions/percentile-disc-transact-sql.md)
  
분석 함수는 행 그룹을 기반으로 집계 값을 계산합니다. 그러나 집계 함수와 달리 분석 함수는 각 그룹에 대해 여러 행을 반환할 수 있습니다. 분석 함수를 사용하면 이동 평균, 누계, 백분율 또는 그룹 내 상위 N개 결과를 컴퓨팅할 수 있습니다.
 
## <a name="see-also"></a>참고 항목

[OVER 절&#40;Transact-SQL&#41;](../../t-sql/queries/select-over-clause-transact-sql.md)