---
title: MSSQLSERVER_10520 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f83b574d6201d0845f23c9194ea2e873d90daa5
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85781485"
---
# <a name="mssqlserver_10520"></a>MSSQLSERVER_10520
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|10520|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|PG_PARAM_NOT_ALLOWED|  
|메시지 텍스트|@type이 '%ls'(으)로 지정되었고 매개 변수 '%ls'에 NULL이 아닌 값이 지정되었으므로 계획 지침 '%.*ls'을(를) 만들 수 없습니다. 이 유형은 매개 변수에 NULL 값이 필요합니다. 매개 변수에 NULL을 지정하거나, 매개 변수에 NULL이 아닌 값을 허용하는 유형으로 유형을 변경하십시오.|  
  
## <a name="explanation"></a>설명  
@type에 지정된 유형에서 지정된 매개 변수에 NULL 값이 필요하지만 NULL이 아닌 값이 지정되었습니다.  
  
## <a name="user-action"></a>사용자 동작  
매개 변수에 NULL을 지정하거나, 매개 변수에 NULL이 아닌 값을 허용하는 유형으로 유형을 변경하십시오.  
  
## <a name="see-also"></a>참고 항목  
[sp_create_plan_guide&#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql.md)  
[계획 지침](~/relational-databases/performance/plan-guides.md)  
  
