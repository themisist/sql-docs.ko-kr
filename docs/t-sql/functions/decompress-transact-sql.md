---
title: DECOMPRESS(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/11/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DECOMPRESS
- DECOMPRESS_TSQL
helpviewer_keywords:
- DECOMPRESS function
ms.assetid: 738d56be-3870-4774-b112-3dce27becc11
author: markingmyname
ms.author: maghan
ms.openlocfilehash: a4c4309a12f3db14af0d38f9e98e73b7e8c4e6b1
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396702"
---
# <a name="decompress-transact-sql"></a>DECOMPRESS(Transact-SQL)
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

이 함수는 GZIP 알고리즘을 사용하여 입력 식 값의 압축을 풉니다. `DECOMPRESS`는 바이트 배열(VARBINARY(MAX) 유형)을 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
DECOMPRESS ( expression )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
 *expression*  
**varbinary(** _n_ **)** , **varbinary(max)** 또는 **binary(** _n_ **)** 값 자세한 내용은 [식 &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)을 참조하세요.  
  
## <a name="return-types"></a>반환 형식  
데이터 형식 **varbinary(max)** 의 값입니다. `DECOMPRESS`는 ZIP 알고리즘을 사용하여 입력 인수의 압축을 풉니다. 필요한 경우 사용자가 명시적으로 결과를 대상 유형으로 캐스팅해야 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="examples"></a>예  
  
### <a name="a-decompress-data-at-query-time"></a>A. 쿼리 시간에 데이터 압축 해제  
이 예제에서는 압축된 테이블 데이터를 반환하는 방법을 보여줍니다.  
  
```  
SELECT _id, name, surname, datemodified,  
             CAST(DECOMPRESS(info) AS NVARCHAR(MAX)) AS info  
FROM player;  
```  
  
### <a name="b-display-compressed-data-using-computed-column"></a>B. 계산 열을 사용하여 압축된 데이터 표시  
이 예에서는 압축 해제된 데이터 스토리지에 대한 테이블을 만드는 방법을 보여줍니다.  
  
```  
CREATE TABLE example_table (  
    _id int primary key identity,  
    name nvarchar(max),  
    surname nvarchar(max),  
    info varbinary(max),  
    info_json as CAST(decompress(info) as nvarchar(max))  
);  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 함수&#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)   
 [COMPRESS&#40;Transact-SQL&#41;](../../t-sql/functions/compress-transact-sql.md)  
  
  
