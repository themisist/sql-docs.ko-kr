---
title: sp_refreshview (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_refreshview
- sp_refreshview_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_refreshview
ms.assetid: 9ce1d07c-ee66-4a83-8c73-cd2cc104dd08
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dbc12b5e9013e8cbb5fb223f473e68c2e1cab445
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891513"
---
# <a name="sp_refreshview-transact-sql"></a>sp_refreshview(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  비스키마 바운드 뷰에 대한 메타데이터를 업데이트합니다. 뷰가 종속된 기본 개체가 변경되면 뷰의 영구 메타데이터가 최신 상태를 유지하지 못할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_refreshview [ @viewname = ] 'viewname'   
```  
  
## <a name="arguments"></a>인수  
`[ @viewname = ] 'viewname'`뷰의 이름입니다. *viewname* 는 **nvarchar**이며 기본값은 없습니다. *viewname* 은 여러 부분으로 된 식별자가 될 수 있지만 현재 데이터베이스의 뷰만 참조할 수 있습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 0이 아닌 수(실패)  
  
## <a name="remarks"></a>설명  
 Schemabinding를 사용 하 여 뷰를 만들지 않은 경우 뷰 정의에 영향을 주는 뷰의 기본 개체가 변경 되 면 **sp_refreshview** 를 실행 해야 합니다. 그렇지 않으면 뷰를 쿼리할 때 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="permissions"></a>사용 권한  
 뷰에 대한 ALTER 권한이 필요하고 뷰 열이 참조하는 CLR(공용 언어 런타임) 사용자 정의 형식 및 XML 스키마 컬렉션에 대한 REFERENCES 권한이 필요합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-updating-the-metadata-of-a-view"></a>A. 뷰의 메타데이터 업데이트  
 다음 예에서는 `Sales.vIndividualCustomer` 뷰의 메타데이터를 새로 고칩니다.  
  
```  
USE AdventureWorks2012;  
GO  
EXECUTE sp_refreshview N'Sales.vIndividualCustomer';  
```  
  
### <a name="b-creating-a-script-that-updates-all-views-that-have-dependencies-on-a-changed-object"></a>B. 변경한 개체에 대해 종속성이 있는 뷰를 모두 업데이트하는 스크립트 만들기  
 `Person.Person` 테이블이 해당 테이블에서 생성된 모든 뷰의 정의에 영향을 주는 방식으로 변경되었다고 가정합니다. 다음 예에서는 `Person.Person` 테이블에 대해 종속성이 있는 모든 뷰의 메타데이터를 새로 고치는 스크립트를 만듭니다.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT DISTINCT 'EXEC sp_refreshview ''' + name + ''''   
FROM sys.objects AS so   
INNER JOIN sys.sql_expression_dependencies AS sed   
    ON so.object_id = sed.referencing_id   
WHERE so.type = 'V' AND sed.referenced_id = OBJECT_ID('Person.Person');  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;저장 프로시저 데이터베이스 엔진](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;&#40;시스템 저장 프로시저](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [sys.sql_expression_dependencies&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md)   
 [Transact-sql&#41;sp_refreshsqlmodule &#40;](../../relational-databases/system-stored-procedures/sp-refreshsqlmodule-transact-sql.md)  
  
  
