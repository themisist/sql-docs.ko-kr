---
title: sp_msx_enlist (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_msx_enlist_TSQL
- sp_msx_enlist
dev_langs:
- TSQL
helpviewer_keywords:
- sp_msx_enlist
ms.assetid: ceb3b2bc-0cc4-48d8-9bdc-6a809556e35f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 551d0796ce534f77d4994064a9af032f34f81f04
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85893470"
---
# <a name="sp_msx_enlist-transact-sql"></a>sp_msx_enlist(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  마스터 서버에서 사용 가능한 서버 목록에 현재 서버를 추가합니다.  
  
> [!CAUTION]  
>  **Sp_msx_enlist** 저장 프로시저는 레지스트리를 편집 합니다. 레지스트리를 잘못 변경하면 시스템에 심각한 구성 문제를 일으키기 때문에 레지스트리를 수동으로 편집하는 것은 좋지 않습니다. 숙련된 사용자만 레지스트리 편집기 프로그램을 사용하여 레지스트리를 편집해야 합니다. 자세한 내용은 Microsoft Windows 설명서를 참조하세요.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_msx_enlist [@msx_server_name =] 'msx_server'   
     [, [@location =] 'location']  
```  
  
## <a name="arguments"></a>인수  
`[ @msx_server_name = ] 'msx_server'`다중 서버 관리 (마스터) 서버의 이름입니다. *msx_server* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @location = ] 'location'`추가할 대상 서버의 위치입니다. *location* 은 **nvarchar (100)** 이며 기본값은 NULL입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 None  
  
## <a name="permissions"></a>사용 권한  
 이 프로시저를 실행할 수 있는 권한은 기본적으로 **sysadmin** 고정 서버 역할의 멤버로 사용 됩니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 현재 서버를 `AdventureWorks1` 마스터 서버에 참여시킵니다. 현재 서버의 위치는 `Building 21, Room 309, Rack 5`입니다.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;sp_msx_defect &#40;](../../relational-databases/system-stored-procedures/sp-msx-defect-transact-sql.md)   
 [Transact-sql&#41;&#40;시스템 저장 프로시저](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;xp_cmdshell &#40;](../../relational-databases/system-stored-procedures/xp-cmdshell-transact-sql.md)  
  
  
