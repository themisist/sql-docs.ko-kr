---
title: MultiPoint | Microsoft 문서
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5551c6547fd93d0d6dce0565e152ba65650b6be7
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85640386"
---
# <a name="multipoint"></a>MultiPoint
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  **MultiPoint** 는 1개 이상의 점 컬렉션입니다. **MultiPoint** 인스턴스의 경계는 비어 있습니다.  
  
## <a name="examples"></a>예  

### <a name="example-a"></a>예 A.
다음 예에서는 SRID가 23이며 두 개의 점이 있는 `geometry MultiPoint` 인스턴스를 만듭니다. 한 점의 좌표는 (2, 3)이고, 다른 한 점의 좌표는 (7, 8)이며, Z 값은 9.5입니다.  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
### <a name="example-b"></a>예 2. 
다음 예제에서는 `STMPointFromText()`를 사용하여 `MultiPoint` 인스턴스를 표현합니다.  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
### <a name="example-c"></a>예 C:
다음 예에서는 `STGeometryN()` 메서드를 사용하여 컬렉션에서 첫째 점의 설명을 검색합니다.  
  
```sql  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a>참고 항목  
 [점](../../relational-databases/spatial/point.md)   
 [공간 데이터&#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)  
  
  
