---
title: sys. dm_pdw_component_health_alerts (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: 88f05392-1e97-4693-ba60-a4910af3c000
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: d0a3d2a3b85f0b6445229812316cf7893badd344
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396646"
---
# <a name="sysdm_pdw_component_health_alerts-transact-sql"></a>sys. dm_pdw_component_health_alerts (Transact-sql)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  어플라이언스 구성 요소에 이전에 발급 된 경고를 저장 합니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|노드의 고유 식별자 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 입니다.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id 및 alert_instance_id이 뷰의 키를 구성 합니다.|NOT NULL|  
|component_id|**int**|구성 요소의 ID입니다. [Pdw_health_components &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md)을 참조 하십시오.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id 및 alert_instance_id이 뷰의 키를 구성 합니다.|NOT NULL|  
|component_instance_id|**nvarchar(255)**|pdw_node_id, component_id, component_instance_id, alert_id 및 alert_instance_id이 뷰의 키를 구성 합니다.|NOT NULL|  
|alert_id|**int**|경고 유형의 ID입니다. [Pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md)을 참조 하십시오.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id 및 alert_instance_id이 뷰의 키를 구성 합니다.|NOT NULL|  
|alert_instance_id|**nvarchar (36)**|지정 된 경고의 인스턴스를 식별 합니다.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id 및 alert_instance_id이 뷰의 키를 구성 합니다.|NOT NULL|  
|previous_value|**nvarchar(255)**|경고가 StatusChange 형식일 때 사용 됩니다. 이전 구성 요소 상태입니다. 임계값 유형의 경고에 대 한 값은 NULL입니다. 경고 유형 목록은 [pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 을 참조 하십시오.|NULL|  
|current_value|**nvarchar(255)**|경고가 StatusChange 형식일 때 사용 됩니다. 현재 구성 요소 상태입니다. 임계값 유형의 경고에 대 한 값은 NULL입니다. 경고 유형 목록은 [pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 을 참조 하십시오.|NULL|  
|create_time|**datetime**|경고가 생성 된 시간 및 날짜입니다.|NOT NULL|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;SQL Data Warehouse 및 병렬 데이터 웨어하우스 동적 관리 뷰](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
