---
title: MSSQLSERVER_21893 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d1ab933d65ab0851f89ea313f87240979adf9288
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85780502"
---
# <a name="mssqlserver_21893"></a>MSSQLSERVER_21893
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|21893|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|SQLErrorNum21893|  
|메시지 텍스트|원래 게시자 '%s'의 구독자(%s)가 리디렉션된 게시자 '%s'에 원격 서버로 표시되지 않습니다. 리디렉션된 게시자에서 **sp_addlinkedserver**를 실행하여 이러한 구독자를 원격 서버로 추가하세요.|  
  
## <a name="explanation"></a>설명  
**sp_addlinkedserver**는 원격 서버에 있는 게시자 데이터베이스의 구독 메타데이터 테이블을 사용하여 연관된 구독자를 식별하고 이러한 구독자에 대해 master.dbo.sysservers에 연관된 항목이 있는지 확인합니다. 이 오류는 식별된 구독자 중 하나라도 없는 경우에 반환됩니다.  
  
이는 오류로 간주되지 않습니다. 이 오류가 발생한 에이전트에서는 이 오류를 정보로 기록하지만 에이전트가 종료되지는 않습니다. 이는 새 게시자에 적절한 구독자 항목이 없더라도 복제에 주는 영향이 적기 때문입니다. sysservers에 구독자에 대한 적절한 항목이 없으면 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]를 통해 일부 구독 관리 작업을 수행할 경우 작업이 실패할 수 있습니다. 하지만 관리 저장 프로시저를 명시적으로 실행하여 동일한 작업을 수행할 수 있습니다.  
  
## <a name="user-action"></a>사용자 동작  
리디렉션된 게시자에서 식별된 각 구독자에 대해 **sp_addlinkedserver**를 실행하여 각각을 원격 서버로 추가합니다. 그런 다음 **sp_serveroption**을 실행하여 서버에 대해 구독자 비트를 설정합니다.  
  
