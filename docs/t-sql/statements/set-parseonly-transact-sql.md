---
title: SET PARSEONLY(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- PARSEONLY_TSQL
- SET_PARSEONLY_TSQL
- PARSEONLY
- SET PARSEONLY
dev_langs:
- TSQL
helpviewer_keywords:
- parsing [SQL Server], SET PARSEONLY statement
- checking syntax
- PARSEONLY option
- syntax [SQL Server], verifying
- verifying syntax
- SET PARSEONLY statement
ms.assetid: 514ab042-c53e-4d96-be71-fb08fcc6ef3c
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 69d2027a590c2e01a409460bce153a850740f36e
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87395098"
---
# <a name="set-parseonly-transact-sql"></a>SET PARSEONLY(Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  각 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문의 구문을 검사한 후 문을 컴파일하거나 실행하지 않고 오류 메시지를 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql
  
SET PARSEONLY { ON | OFF }  
```  
  
## <a name="remarks"></a>설명  
 SET PARSEONLY 옵션이 ON이면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]가 문을 구문 분석만 합니다. When SET PARSEONLY is OFF, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]는 해당 명령문을 컴파일하고 실행합니다.  
  
 SET PARSEONLY 옵션은 구문 분석 시에 설정되며, 실행 시 또는 런타임에는 설정되지 않습니다.  
  
 저장 프로시저나 트리거에서는 PARSEONLY를 사용하지 않습니다. OFFSETS 옵션이 ON으로 설정되어 있고 오류가 발생하지 않으면 SET PARSEONLY가 오프셋을 반환합니다.  
  
## <a name="permissions"></a>사용 권한  
 **public** 역할의 멤버 자격이 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SET 문&#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)   
 [SET OFFSETS&#40;Transact-SQL&#41;](../../t-sql/statements/set-offsets-transact-sql.md)  
  
  
