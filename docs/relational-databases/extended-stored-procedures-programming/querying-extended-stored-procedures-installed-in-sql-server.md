---
title: 확장 저장 프로시저 쿼리
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.custom: seo-dt-2019
ms.openlocfilehash: 8413f071cfb36f5cad9130d3e2b56327d9b3bf45
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85758090"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a>SQL Server에 설치된 확장 저장 프로시저 쿼리
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 대신 CLR 통합을 사용하세요.  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인증 된 사용자는 **sp_helpextendedproc** 시스템 프로시저를 실행 하 여 현재 정의 된 확장 저장 프로시저와 각가 속한 DLL의 이름을 표시할 수 있습니다. 예를 들어 다음 예에서는 **xp_hello** 속한 DLL을 반환 합니다.  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 확장 저장 프로시저를 지정 하지 않고 **sp_helpextendedproc** 를 실행 하면 모든 확장 저장 프로시저와 해당 dll이 표시 됩니다.  
  
> [!IMPORTANT]  
>  로그인한 사용자가 소유하거나 권한이 있는 확장 저장 프로시저에 대해서만 정보가 반환됩니다. **Sysadmin** 고정 서버 역할의 멤버와 **db_owner**, **db_securityadmin**및 **db_ddladmin** 고정 데이터베이스 역할의 멤버만이 모든 확장 저장 프로시저에 대 한 정보를 볼 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;sp_helpextendedproc &#40;](../../relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql.md)   
 [Transact-sql&#41;sp_addextendedproc &#40;](../../relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql.md)   
 [sp_dropextendedproc&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql.md)  
  
  
