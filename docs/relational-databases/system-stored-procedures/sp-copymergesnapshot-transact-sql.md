---
title: sp_copymergesnapshot (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_copymergesnapshot
- sp_copymergesnapshot_TSQL
helpviewer_keywords:
- sp_copymergesnapshot
ms.assetid: eaecd6e0-8486-4e5d-ace7-8ae75768c0a8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 64d4a6bb067c53b13592074fc1c08b2e35fc4830
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85771227"
---
# <a name="sp_copymergesnapshot-transact-sql"></a>sp_copymergesnapshot(Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  지정 된 게시의 스냅숏 폴더를 ** \@ destination_folder**에 나열 된 폴더로 복사 합니다. 이 저장 프로시저는 게시 데이터베이스의 게시자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_copymergesnapshot [ @publication = ] 'publication', [ @destination_folder = ] 'destination_folder'  
```  
  
## <a name="arguments"></a>인수  
`[ @publication = ] 'publication'`스냅숏 내용을 복사할 게시의 이름입니다. *게시* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @destination_folder = ] 'destination_folder'`게시 스냅숏의 내용을 복사할 대상 폴더의 이름입니다. *destination_folder*은 **nvarchar (255)** 이며 기본값은 없습니다. *Destination_folder* 는 다른 서버, 네트워크 드라이브 또는 이동식 미디어 (cd-rom 또는 이동식 디스크 등)와 같은 대체 위치가 될 수 있습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>설명  
 **sp_copymergesnapshot** 는 병합 복제에 사용 됩니다. [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 버전 7.0 및 이전 버전을 실행 하는 구독자는 대체 스냅숏 위치를 사용할 수 없습니다.  
  
## <a name="permissions"></a>사용 권한  
 **Sysadmin** 고정 서버 역할 또는 **db_owner** 고정 데이터베이스 역할의 멤버만 **sp_copymergesnapshot**을 실행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [대체 스냅숏 폴더 위치](../../relational-databases/replication/snapshot-options.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
