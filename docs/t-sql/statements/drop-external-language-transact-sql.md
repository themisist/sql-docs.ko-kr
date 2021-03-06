---
title: DROP EXTERNAL LANGUAGE(Transact-SQL) - SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 08/08/2019
ms.prod: sql
ms.technology: language-extensions
ms.topic: language-reference
author: nelgson
ms.author: negust
ms.reviewer: dphansen
manager: cgronlun
monikerRange: '>=sql-server-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 6f4b6ee38ed70da600ef007f168cd7e95a010278
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85766365"
---
# <a name="drop-external-library-transact-sql"></a>DROP EXTERNAL LIBRARY(Transact-SQL)  
[!INCLUDE[SQL Server 2019](../../includes/applies-to-version/sqlserver2019.md)]

기존 외부 언어를 삭제합니다.

## <a name="syntax"></a>구문

```text
DROP EXTERNAL LANGUAGE <language_name>
```

### <a name="arguments"></a>인수

**language_name**

언어는 데이터베이스 범위 개체입니다. 언어 이름은 데이터베이스 내에서 고유해야 합니다.

## <a name="permissions"></a>사용 권한

언어를 삭제하려면 ALTER ANY EXTERNAL LANGUAGE 권한이 필요합니다. 기본적으로 모든 데이터베이스 소유자 또는 개체 소유자는 외부 언어도 삭제할 수 있습니다.

> [!NOTE]
> 외부 언어를 제거하기 전에 외부 언어를 참조하는 외부 라이브러리를 제거해야 합니다.

### <a name="return-values"></a>반환 값

정보 메시지는 명령문이 성공한 경우 반환됩니다.

## <a name="remarks"></a>설명

외부 언어를 삭제하기 전에 지정된 언어에 대한 모든 외부 라이브러리를 삭제해야 합니다.

## <a name="examples"></a>예

외부 언어 **Java** 만들기:

```sql
CREATE EXTERNAL LANGUAGE Java 
FROM (CONTENT = N'<path-to-zip>', FILE_NAME = 'javaextension.dll');
GO
```

외부 언어 삭제:

```sql
DROP EXTERNAL LANGUAGE Java;
```

## <a name="see-also"></a>참고 항목

[CREATE EXTERNAL LANGUAGE(Transact-SQL)](create-external-language-transact-sql.md)  
[ALTER EXTERNAL LANGUAGE(Transact-SQL)](alter-external-language-transact-sql.md)  
[sys.external_languages](../../relational-databases/system-catalog-views/sys-external-languages-transact-sql.md)  
[sys.external_language_files](../../relational-databases/system-catalog-views/sys-external-language-files-transact-sql.md)  
