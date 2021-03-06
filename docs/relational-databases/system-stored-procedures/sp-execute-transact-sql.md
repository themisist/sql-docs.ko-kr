---
title: sp_execute (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursor_execute
- sp_cursor_execute_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_execute
ms.assetid: 2009acd3-0d92-435a-a8fb-057e50dc7146
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 12bfa6e7d37aae2a5ffc58828d47ace11d558487
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87392999"
---
# <a name="sp_execute-transact-sql"></a>sp_execute(Transact-SQL)
[!INCLUDE [sql-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdbmi-asa-pdw.md)]

  [!INCLUDE[tsql](../../includes/tsql-md.md)]지정 된 핸들 및 선택적 매개 변수 값을 사용 하 여 준비 된 문을 실행 합니다. sp_execute은 TDS (tabular data stream) 패킷에서 ID = 12를 지정 하 여 호출 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
sp_execute handle OUTPUT  
    [,bound_param  ]  [,...n ]  ]  
```  
  
## <a name="arguments"></a>인수  
 *처리*  
 Sp_prepare에서 반환 하는 *핸들* 값입니다. *handle* 은 **int** 입력 값에 대해를 호출 하는 필수 매개 변수입니다.  
  
 *bound_param*  
 추가 매개 변수의 사용을 나타냅니다. *bound_param* 은 프로시저에 대 한 추가 매개 변수를 나타내기 위해 모든 데이터 형식의 입력 값을 호출 하는 필수 매개 변수입니다.  
  
> [!NOTE]  
>  *bound_param* 은 sp_prepare*params* 값에 의해 생성 된 선언과 일치 해야 하며 * @name = value* 또는 *value*형식으로 지정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;시스템 저장 프로시저](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [sp_prepare &#40;SQL&#41;](../../relational-databases/system-stored-procedures/sp-prepare-transact-sql.md)  
  
  
