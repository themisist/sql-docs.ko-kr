---
title: MSSQLSERVER_1401 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c656780c4ef64584f9ce6c28a183a9c9b821619
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85781067"
---
# <a name="mssqlserver_1401"></a>MSSQLSERVER_1401
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|1401|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|DBM_MASTERSTARTUP|  
|메시지 텍스트|다음과 같은 이유로 인해 데이터베이스 미러링 마스터 스레드 루틴을 시작하지 못했습니다: %ls. 이 오류의 원인을 수정한 다음 SQL Server 서비스를 다시 시작하십시오.|  
  
## <a name="explanation"></a>설명  
미러링 제어 스레드를 시작하지 못했습니다.  
  
## <a name="user-action"></a>사용자 동작  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 오류 로그에서 이 메시지 이전에 발생한 관련 오류를 찾으십시오. 이 오류의 원인을 수정한 다음 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 서비스(MSSQLSERVER)를 다시 시작하세요.  
  
## <a name="see-also"></a>참고 항목  
[데이터베이스 엔진, SQL Server 에이전트 또는 SQL Server Browser 서비스 시작, 중지, 일시 중지, 재개 및 다시 시작](~/database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
