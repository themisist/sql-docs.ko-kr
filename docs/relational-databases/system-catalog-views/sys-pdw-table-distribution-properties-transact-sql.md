---
title: sys. pdw_table_distribution_properties (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 12/03/2019
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 639a7475-7c92-41e0-a8ab-ad630eb5aea3
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: b0e93eebd56579785a2673f4a38846350c737c3f
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86196820"
---
# <a name="syspdw_table_distribution_properties-transact-sql"></a>sys. pdw_table_distribution_properties (Transact-sql)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  테이블에 대 한 배포 정보를 저장 합니다.  
  
|열 이름|데이터 형식|설명|범위|  
|-----------------|---------------|-----------------|-----------|  
|**object_id**|**int**|등록 된 속성이 지정 된 테이블의 ID입니다.||  
|**distribution_policy**|**tinyint**|0 = 정의 되지 않음<br /><br /> 1 = 없음<br /><br /> 2 = 해시<br /><br /> 3 = 복제<br /><br /> 4 = ROUND_ROBIN||  
|**distribution_policy_desc**|**nvarchar(60)**|정의 되지 않음, 없음, 해시, 복제, ROUND_ROBIN|[!INCLUDE[ssSDW](../../includes/sssdw-md.md)]HASH, ROUND_ROBIN 또는 복제 중 하나를 반환 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SQL Data Warehouse 및 병렬 Data Warehouse 카탈로그 뷰](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
