---
title: AUTO_SHRINK 데이터베이스 옵션을 OFF로 설정 | Microsoft 문서
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fac9ff925c5e24d21efe0dcb5b7776636cf78572
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85774194"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a>AUTO_SHRINK 데이터베이스 옵션을 OFF로 설정
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  이 규칙은 AUTO_SHRINK 데이터베이스 옵션이 OFF로 설정되었는지 검사합니다. 데이터베이스를 자주 축소 및 확장하면 물리적 조각화가 발생할 수 있습니다.  
  
## <a name="best-practices-recommendations"></a>최선의 구현 방법 권장 사항  
 AUTO_SHRINK 데이터베이스 옵션을 OFF로 설정합니다. 회수 중인 공간이 이후에 필요하지 않다면 데이터베이스를 수동으로 축소하여 해당 공간을 회수할 수 있습니다.  
  
## <a name="for-more-information"></a>참조 항목  
 Microsoft 기술 자료 문서 [315512](https://go.microsoft.com/fwlink/?linkid=117750)  
  
## <a name="see-also"></a>참고 항목  
 [정책 기반 관리를 사용하여 최선의 방법 모니터링 및 적용](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
