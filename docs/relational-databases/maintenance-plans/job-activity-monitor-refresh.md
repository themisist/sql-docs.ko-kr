---
title: 작업 활동 모니터 새로 고침 | Microsoft 문서
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql13.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6343929a2f893d020d992a7bd68ba70e178ed2c3
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85666915"
---
# <a name="job-activity-monitor-refresh"></a>작업 활동 모니터 새로 고침
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  **새로 고침 설정** 대화 상자를 사용하여 작업 활동 모니터가 서버 작업에 대한 새로운 정보를 가져오는 간격을 구성할 수 있습니다. 작업 활동 모니터 표에 정보를 가져오려면 작업 활동 모니터가 모니터링하는 서버에 대해 쿼리를 실행해야 합니다. 자동 새로 고침 간격을 30초보다 작게 설정하면 이러한 쿼리를 실행하는 데 사용되는 시간이 서버 성능에 영향을 줄 수 있습니다.  
  
 이 대화 상자를 열려면 작업 활동 모니터에서 **상태**섹션의 **새로 고침 설정 보기** 를 클릭합니다.  
  
## <a name="options"></a>옵션  
 **자동 새로 고침 간격**  
 작업 모니터 정보의 자동 새로 고침을 시작하려면 선택합니다. 이 옵션은 기본적으로 해제되어 있습니다.  
  
 **초**  
 자동 새로 고침 시도 간격(초)입니다. 기본값은 60초입니다. 5 이하로 설정하면 5초마다 새로 고쳐집니다.  
  
## <a name="see-also"></a>참고 항목  
 [작업 활동 모니터링](../../ssms/agent/monitor-job-activity.md)  
  
  
