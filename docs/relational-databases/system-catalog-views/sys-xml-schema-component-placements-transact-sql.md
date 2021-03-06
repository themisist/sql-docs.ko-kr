---
title: sys.xml_schema_component_placements (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_component_placements
- xml_schema_component_placements_TSQL
- xml_schema_component_placements
- sys.xml_schema_component_placements_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_component_placements catalog view
ms.assetid: 2d3c8828-e4b3-423d-bf11-990464c1341b
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
ms.openlocfilehash: f63f2eee6898a3b20eeef21804f3ef3441ddc1c8
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85900616"
---
# <a name="sysxml_schema_component_placements-transact-sql"></a>sys.xml_schema_component_placements(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  각 XML 스키마 구성 요소 배치에 대해 행을 반환합니다.  
   
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**xml_component_id**|**int**|이 배치를 소유한 XML 스키마 구성 요소의 ID입니다.|  
|**placement_id**|**int**|배치의 ID입니다. 소유한 XML 스키마 구성 요소 내에서 고유합니다.|  
|**placed_xml_component_id**|**int**|배치된 XML 스키마 구성 요소의 ID입니다.|  
|**is_default_fixed**|**bit**|1 = 기본값이 고정 값입니다. XML 인스턴스에서 이 값을 무시할 수 없습니다.<br /><br /> 0 = 이 값을 무시할 수 있습니다(기본값).|  
|**min_occurrences**|**int**|배치된 구성 요소의 최소 발생 횟수입니다.|  
|**max_occurrences**|**int**|배치된 구성 요소의 최대 발생 횟수입니다.|  
|**default_value**|**nvarchar(4000)**|기본값을 제공한 경우 기본값입니다. 기본값을 제공하지 않으면 NULL입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;카탈로그 뷰](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Xml 스키마 &#40;XML 형식 시스템&#41; 카탈로그 뷰 &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)  
  
  
