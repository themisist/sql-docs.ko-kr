---
title: MSSQLSERVER_1105 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a9a842f146ed21c44c411beeabf3c94d705a6b33
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85781264"
---
# <a name="mssqlserver_1105"></a>MSSQLSERVER_1105
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|1105|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|NO_MORE_SPACE_IN_FG|  
|메시지 텍스트|'%.\*ls' 파일 그룹이 꽉 찼으므로 데이터베이스 '%.\*ls'의 개체 %.*ls'%.\*ls에 공간을 할당할 수 없습니다. 필요 없는 파일을 삭제하거나, 파일 그룹의 개체를 삭제하거나, 파일 그룹에 파일을 추가하거나, 파일 그룹의 기존 파일에 대해 자동 증가를 설정하여 디스크 공간을 만드세요.|  
  
## <a name="explanation"></a>설명  
파일 그룹에 사용 가능한 디스크 공간이 없습니다.  
  
## <a name="user-action"></a>사용자 동작  
다음 동작으로 파일 그룹에 사용 가능한 공간을 만들 수 있습니다.  
  
-   자동 증가를 설정합니다.  
  
-   파일에 파일 추가  
  
-   더 이상 필요하지 않은 인덱스나 테이블을 삭제하여 디스크 공간을 비웁니다.  
  
-   자세한 내용은 SQL Server 온라인 도움말의 "데이터 디스크 공간 부족 문제 해결"을 참조하세요.  
  
> [!NOTE]  
> 인덱스가 여러 파일에 있을 때, 파일 중 하나가 가득 차면 **ALTER INDEX REORGANIZE**가 1105 오류를 반환할 수 있습니다. 프로세스에서 가득 찬 파일로 행을 이동하려 하면 재구성 프로세스는 차단됩니다. 이 제한을 해결하려면 **ALTER INDEX REORGANIZE** 대신 **ALTER INDEX REBUILD**를 수행하거나 가득 찬 파일의 파일 증가 제한을 늘립니다.  
  
