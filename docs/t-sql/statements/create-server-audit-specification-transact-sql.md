---
title: CREATE SERVER AUDIT SPECIFICATION(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CREATE_SERVER_AUDIT_SPECIFICATION_TSQL
- CREATE SERVER AUDIT SPECIFICATION
dev_langs:
- TSQL
helpviewer_keywords:
- CREATE SERVER AUDIT SPECIFICATION statement
ms.assetid: db77fa77-fedb-40ac-83e6-06343063e518
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6cc72e48eea68aa97323fc30bdad083fd79d391e
ms.sourcegitcommit: cb620c77fe6bdefb975968837706750c31048d46
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86392951"
---
# <a name="create-server-audit-specification-transact-sql"></a>CREATE SERVER AUDIT SPECIFICATION(Transact-SQL)
[!INCLUDE [SQL Server - ASDBMI](../../includes/applies-to-version/sql-asdbmi.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Audit 기능을 사용하여 서버 감사 사양 개체를 만듭니다. 자세한 내용은 [SQL Server Audit&#40;데이터베이스 엔진&#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md)을 참조하세요.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql
  
CREATE SERVER AUDIT SPECIFICATION audit_specification_name  
FOR SERVER AUDIT audit_name  
{  
    { ADD ( { audit_action_group_name } )   
    } [, ...n]  
    [ WITH ( STATE = { ON | OFF } ) ]  
}  
[ ; ]  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
 *audit_specification_name*  
 서버 감사 사양의 이름입니다.  
  
 *audit_name*  
 이 사양이 적용되는 감사의 이름입니다.  
  
 *audit_action_group_name*  
 서버 수준 감사 가능 동작 그룹의 이름입니다. 감사 동작 그룹의 목록에 대해서는 [SQL Server 감사 동작 그룹 및 동작](../../relational-databases/security/auditing/sql-server-audit-action-groups-and-actions.md)을 참조합니다.  
  
 WITH **(** STATE **=** { ON | OFF } **)**  
 감사에서 이 감사 사양에 대한 레코드를 수집하거나 수집하지 못하도록 설정합니다.  
  
## <a name="remarks"></a>설명  
 감사가 있어야 이에 대한 서버 감사 사양을 만들 수 있습니다. 서버 감사 사양을 처음 만들 때는 사용할 수 없는 상태입니다.  
  
## <a name="permissions"></a>사용 권한  
 ALTER ANY SERVER AUDIT 권한이 있는 사용자는 서버 감사 사양을 만들어 모든 감사에 바인딩할 수 있습니다.  
  
 만든 서버 감사 사양은 CONTROL SERVER 또는 ALTER ANY SERVER AUDIT 권한이 있는 보안 주체, sysadmin 계정 또는 감사에 대한 명시적인 액세스가 있는 보안 주체가 볼 수 있습니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `HIPAA_Audit_Specification`라는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Audit에 대해 실패한 로그인을 감사하는 `HIPAA_Audit`이라는 서버 감사 사양을 만듭니다.  
  
```  
CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
FOR SERVER AUDIT HIPAA_Audit  
    ADD (FAILED_LOGIN_GROUP)  
    WITH (STATE=ON);  
GO  
```  
  
 감사를 만드는 방법에 대한 전체 예에 대해서는 [SQL Server Audit &#40;Database Engine&#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md)를 참조하십시오.  
   
## <a name="see-also"></a>참고 항목  
 [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](../../t-sql/statements/create-server-audit-transact-sql.md)   
 [ALTER SERVER AUDIT  &#40;Transact-SQL&#41;](../../t-sql/statements/alter-server-audit-transact-sql.md)   
 [DROP SERVER AUDIT  &#40;Transact-SQL&#41;](../../t-sql/statements/drop-server-audit-transact-sql.md)   
 [ALTER SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-server-audit-specification-transact-sql.md)   
 [DROP SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-server-audit-specification-transact-sql.md)   
 [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](../../t-sql/statements/create-database-audit-specification-transact-sql.md)   
 [ALTER DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-audit-specification-transact-sql.md)   
 [DROP DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-audit-specification-transact-sql.md)   
 [ALTER AUTHORIZATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-authorization-transact-sql.md)   
 [sys.fn_get_audit_file &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-get-audit-file-transact-sql.md)   
 [sys.server_audits &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-audits-transact-sql.md)   
 [sys.server_file_audits &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-file-audits-transact-sql.md)   
 [sys.server_audit_specifications &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-audit-specifications-transact-sql.md)   
 [sys.server_audit_specification_details &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-audit-specification-details-transact-sql.md)   
 [sys.database_audit_specifications &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-audit-specifications-transact-sql.md)   
 [sys.database_audit_specification_details &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-audit-specification-details-transact-sql.md)   
 [sys.dm_server_audit_status &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-audit-status-transact-sql.md)   
 [sys.dm_audit_actions &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-audit-actions-transact-sql.md)   
 [서버 감사 및 서버 감사 사양 만들기](../../relational-databases/security/auditing/create-a-server-audit-and-server-audit-specification.md)  
  
  
