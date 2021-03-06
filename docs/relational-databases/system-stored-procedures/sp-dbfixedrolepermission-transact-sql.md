---
title: sp_dbfixedrolepermission (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbfixedrolepermission
- sp_dbfixedrolepermission_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dbfixedrolepermission
ms.assetid: b8c30191-f532-49cd-83f3-c271f63ce572
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 69c80caccabb81fd2da1b3bdbe13ada8c5aa2582
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85867677"
---
# <a name="sp_dbfixedrolepermission-transact-sql"></a>sp_dbfixedrolepermission(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  고정 데이터베이스 역할에 대한 사용 권한을 표시합니다. **sp_dbfixedrolepermission** 는에서 올바른 정보를 반환 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] 합니다. 출력에는 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]에서 구현된 사용 권한 계층 구조의 변경 내용은 출력에 반영되지 않습니다. 자세한 내용은 고정 데이터베이스 역할의 목록과 해당 권한이 있는 [데이터베이스 수준 역할](../../relational-databases/security/authentication-access/database-level-roles.md#fixed-database-roles)을 참조 하세요.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_dbfixedrolepermission [ [ @rolename = ] 'role' ]  
```  
  
## <a name="arguments"></a>인수  
`[ @rolename = ] 'role'`유효한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 고정 데이터베이스 역할의 이름입니다. *role* 은 **sysname**이며 기본값은 NULL입니다. *Role* 을 지정 하지 않으면 모든 고정 데이터베이스 역할에 대 한 사용 권한이 표시 됩니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**DbFixedRole**|**sysname**|고정 데이터베이스 역할의 이름입니다.|  
|**사용 권한**|**nvarchar (70)**|**Dbfixedrole** 과 관련 된 사용 권한|  
  
## <a name="remarks"></a>설명  
 고정 데이터베이스 역할의 목록을 표시 하려면 **sp_helpdbfixedrole**를 실행 합니다. 다음 표에서는 고정 데이터베이스 역할을 보여 줍니다.  
  
|고정 데이터베이스 역할|Description|  
|-------------------------|-----------------|  
|**db_owner**|데이터베이스 소유자입니다.|  
|**db_accessadmin**|데이터베이스 액세스 관리자입니다.|  
|**db_securityadmin**|데이터베이스 보안 관리자입니다.|  
|**db_ddladmin**|데이터베이스 DDL(데이터 정의 언어) 관리자입니다.|  
|**db_backupoperator**|데이터베이스 백업 운영자입니다.|  
|**db_datareader**|데이터베이스의 데이터 판독기입니다.|  
|**db_datawriter**|데이터베이스의 데이터 기록기입니다.|  
|**db_denydatareader**|데이터베이스의 거부 데이터 판독기입니다.|  
|**db_denydatawriter**|데이터베이스의 거부 데이터 기록기입니다.|  
  
 **Db_owner** 고정 데이터베이스 역할의 멤버에 게는 다른 모든 고정 데이터베이스 역할의 사용 권한이 있습니다. 고정 서버 역할에 대 한 사용 권한을 표시 하려면 **sp_srvrolepermission**를 실행 합니다.  
  
 결과 집합에는 데이터베이스 역할의 멤버에 의해 수행되는 기타 특수한 작업뿐만 아니라 실행될 수 있는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 포함됩니다.  
  
## <a name="permissions"></a>사용 권한  
 **public** 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 쿼리는 고정 데이터베이스 역할을 지정하지 않았기 때문에 모든 고정 데이터베이스 역할에 대한 사용 권한을 반환합니다.  
  
```  
EXEC sp_dbfixedrolepermission;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;보안 저장 프로시저](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;sp_addrolemember &#40;](../../relational-databases/system-stored-procedures/sp-addrolemember-transact-sql.md)   
 [Transact-sql&#41;sp_droprolemember &#40;](../../relational-databases/system-stored-procedures/sp-droprolemember-transact-sql.md)   
 [Transact-sql&#41;sp_helpdbfixedrole &#40;](../../relational-databases/system-stored-procedures/sp-helpdbfixedrole-transact-sql.md)   
 [Transact-sql&#41;sp_srvrolepermission &#40;](../../relational-databases/system-stored-procedures/sp-srvrolepermission-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
