---
title: Null(geography 데이터 형식) | Miciosoft Docs
ms.custom: ''
ms.date: 07/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Null (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- Null (geography Data Type)
- Null method
ms.assetid: bb464b06-86e0-4b8b-ad78-04bd33b6069c
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4896de83781df95d4c3cbd673e866e51c04bd5fe
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86552526"
---
# <a name="null-geography-data-type"></a>Null(geography 데이터 형식)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

**geography** 형식의 null 인스턴스를 제공하는 읽기 전용 속성입니다.
  
## <a name="syntax"></a>구문  
  
```  
  
Null  
```  

[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 형식: **geography**  
  
 CLR 형식: **SqlGeography**  
  
## <a name="remarks"></a>설명  
  
## <a name="examples"></a>예  
 다음 예에서는 Null `geography` 인스턴스를 검색합니다.  
  
```  
DECLARE @g geography;   
SET @g = geography::[Null];  
SELECT @g  
```  
  
## <a name="see-also"></a>참고 항목  
 [확장 정적 지리 메서드](../../t-sql/spatial-geography/extended-static-geography-methods.md)  
  
  
