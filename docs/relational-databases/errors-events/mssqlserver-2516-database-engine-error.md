---
title: MSSQLSERVER_2516 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fd78d5bbe75e544c4b3f1c9cadc4a5656dc72a9c
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85780400"
---
# <a name="mssqlserver_2516"></a>MSSQLSERVER_2516
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|2516|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|DBCC_REPAIR_DIFF_MAP_INVALIDATED|  
|메시지 텍스트|복구로 인해 데이터베이스 NAME에 대한 차등 비트맵이 무효화되었습니다. 차등 백업 체인이 끊어졌습니다. 차등 백업을 수행하려면 전체 데이터베이스 백업을 수행해야 합니다.|  
  
## <a name="explanation"></a>설명  
MSSQLEngine_2515 오류가 복구되면 이 정보 메시지가 반환됩니다.  
  
## <a name="user-action"></a>사용자 동작  
전체 데이터베이스 백업을 수행합니다.  
  
## <a name="see-also"></a>참고 항목  
[전체 데이터베이스 백업 만들기&#40;SQL Server&#41;](~/relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
