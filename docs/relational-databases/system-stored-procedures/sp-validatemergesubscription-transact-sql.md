---
title: sp_validatemergesubscription (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_validatemergesubscription
- sp_validatemergesubscription_TSQL
helpviewer_keywords:
- sp_validatemergesubscription
ms.assetid: d73ad03c-e5b3-4606-a0ee-7d75e12762a6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 27bb4de88fcdde6dfe32729a5a68f53fba79f9b2
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891228"
---
# <a name="sp_validatemergesubscription-transact-sql"></a>sp_validatemergesubscription(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  지정한 구독에 대해 유효성 검사를 수행합니다. 이 저장 프로시저는 게시 데이터베이스의 게시자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_validatemergesubscription [@publication=] 'publication'  
        , [ @subscriber = ] 'subscriber'  
        , [ @subscriber_db = ] 'subscriber_db'  
        , [ @level = ] level  
```  
  
## <a name="arguments"></a>인수  
`[ @publication = ] 'publication'`게시의 이름입니다. *게시* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @subscriber = ] 'subscriber'`구독자의 이름입니다. *구독자* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @subscriber_db = ] 'subscriber_db'`구독 데이터베이스의 이름입니다. *subscriber_db* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @level = ] 'level'`수행할 유효성 검사의 유형입니다. *level* 은 **tinyint**이며 기본값은 없습니다. 수준은 다음 값 중 하나일 수 있습니다.  
  
|수준 값|Description|  
|-----------------|-----------------|  
|**1**|행 개수의 유효성만 검사합니다.|  
|**2**|행 개수 및 체크섬의 유효성을 검사합니다.|  
|**3**|행 개수 및 이진 체크섬의 유효성을 검사합니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>설명  
 **sp_validatemergesubscription** 는 병합 복제에 사용 됩니다.  
  
## <a name="permissions"></a>사용 권한  
 **Sysadmin** 고정 서버 역할 또는 **db_owner** 고정 데이터베이스 역할의 멤버만 **sp_validatemergesubscription**을 실행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;를 &#40;하는 복제 저장 프로시저](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [복제 된 데이터의 유효성 검사](../../relational-databases/replication/validate-data-at-the-subscriber.md)   
 [Transact-sql&#41;sp_validatemergepublication &#40;](../../relational-databases/system-stored-procedures/sp-validatemergepublication-transact-sql.md)  
  
  
