---
title: MSSQLSERVER_9002 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6e888a44cd96eeaa93f49c02128e48763b66a9ee
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85636640"
---
# <a name="mssqlserver_9002"></a>MSSQLSERVER_9002
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|9002|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|LOG_IS_FULL|  
|메시지 텍스트|데이터베이스 '%.*ls'의 트랜잭션 로그가 꽉 찼습니다. 로그의 공간을 다시 사용할 수 없는 이유를 확인하려면 sys.databases의 log_reuse_wait_desc 열을 참조하십시오.|  
  
## <a name="explanation"></a>설명  
데이터베이스 로그에 공간이 부족합니다. **sys.databases**의 **log_reuse_wait_desc** 열을 확인하여 로그의 공간을 다시 사용할 수 없는 이유를 알 수 있습니다.  
  
## <a name="user-action"></a>사용자 동작  
**sys.databases**를 사용하여 로그가 꽉 찬 이유를 확인하고 문제를 해결하세요. 자세한 내용은 SQL Server 온라인 설명서의 "꽉 찬 트랜잭션 로그 문제 해결(오류 9002)"을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
[꽉 찬 트랜잭션 로그 문제 해결&#40;SQL Server 오류 9002&#41;](~/relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
[sys.databases&#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/sys-databases-transact-sql.md)  
  
