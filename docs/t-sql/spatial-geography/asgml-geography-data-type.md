---
title: AsGml(geography 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- AsGml_(geography_Data_Type)_TSQL
- AsGml
- AsGml_TSQL
- AsGml (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- AsGml method
ms.assetid: 67795c64-d8d3-48dc-93ef-3c8a9274deb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f6b4dc7090262a11d17239d8be50c72a637b04f3
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555541"
---
#  <a name="asgml---geography-data-type"></a>AsGml(geography 데이터 형식)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  **geography** 인스턴스의 GML(Geography Markup Language) 표현을 반환합니다.  
  
 Geography Markup Language에 대한 자세한 내용은 Open Geospatial Consortium 사양: [OGC 사양, Geography Markup Language](https://go.microsoft.com/fwlink/?LinkId=93629)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
  
.AsGml ( )  
```  

[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **xml**  
  
 CLR 반환 형식: **SqlXml**  
  
## <a name="remarks"></a>설명  
  
## <a name="examples"></a>예  
 다음 예에서는 `LineString` 인스턴스를 만들고 `AsGML()`을 사용하여 인스턴스의 GML 설명을 반환합니다.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.AsGml();  
```  
  
 이 메서드는 `LineString` 인스턴스로 설명을 반환합니다.  
  
```  
<LineString xmlns="https://www.opengis.net/gml"><posList>47.656 -122.36 47.656 -122.343</posList></LineString>  
```  
  
## <a name="see-also"></a>참고 항목  
 [지리 인스턴스의 확장 메서드](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  
