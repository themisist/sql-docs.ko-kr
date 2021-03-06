---
title: sp_clean_db_file_free_space (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_clean_db_file_free_space
- sp_clean_db_file_free_space_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ghost records
- sp_clean_db_file_free_space
ms.assetid: 3eb53a67-969d-4cb8-9681-b1c8e6fd55b6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c45d25dd63149145fc732642b873bc4e7a6193
ms.sourcegitcommit: d855def79af642233cbc3c5909bc7dfe04c4aa23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87122464"
---
# <a name="sp_clean_db_file_free_space-transact-sql"></a>sp_clean_db_file_free_space(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 데이터 수정 루틴 때문에 데이터베이스 페이지에 남겨진 정보를 제거합니다. sp_clean_db_file_free_space는 데이터베이스의 파일 하나에서만 모든 페이지를 정리합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql  
sp_clean_db_file_free_space   
  [ @dbname = ] 'database_name'   
  , [ @fileid = ] 'file_number'   
  [ , [ @cleaning_delay = ] 'delay_in_seconds' ] [;]  
```  
  
## <a name="arguments"></a>인수  
 @dbname= '*database_name*'  
 정리할 데이터베이스의 이름입니다. *dbname* 은 **sysname** 이며 NULL 일 수 없습니다.  
  
 @fileid= '*file_number*'  
 정리할 데이터 파일 ID입니다. *file_number* 는 **int** 이며 NULL 일 수 없습니다.  
  
 @cleaning_delay= '*delay_in_seconds*'  
 페이지 정리를 멈추고 대기할 시간 간격을 지정합니다. 이 간격을 지정하면 I/O 시스템에 미치는 영향을 줄이는 데 도움이 됩니다. *delay_in_seconds* 은 **int** 이며 기본값은 0입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="remarks"></a>설명  
 테이블에서 삭제 작업을 수행하거나 업데이트 작업으로 행을 이동하면 행에 대한 참조를 제거하여 페이지에서 공간을 즉시 확보할 수 있습니다. 그러나 상황에 따라서는 행이 데이터 페이지에 물리적으로 남아 있어 삭제해야 할 레코드가 될 수 있습니다. 삭제할 레코드는 백그라운드 프로세스를 통해 정기적으로 제거됩니다. 이 잔여 데이터는 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 쿼리에 대 한 응답으로에서 반환 되지 않습니다. 그러나 데이터 나 백업 파일의 물리적 보안이 위험에 노출 되는 환경에서는를 사용 `sp_clean_db_file_free_space` 하 여 이러한 고스트 레코드를 정리할 수 있습니다. 모든 데이터베이스 파일에 대해 한 번에이 작업을 수행 하려면 [sp_clean_db_free_space (transact-sql)](../../relational-databases/system-stored-procedures/sp-clean-db-free-space-transact-sql.md)를 사용 합니다. 
  
 sp_clean_db_file_free_space를 실행하는 데 필요한 시간은 파일의 크기, 사용 가능한 여유 공간, 디스크의 용량에 따라 달라집니다. 실행 중에는 i/o `sp_clean_db_file_free_space` 작업에 상당한 영향을 줄 수 있으므로 일반적인 작업 시간 외에이 절차를 실행 하는 것이 좋습니다.  
  
 을 실행 하기 전에 `sp_clean_db_file_free_space` 전체 데이터베이스 백업을 만드는 것이 좋습니다.  
  
 관련 [sp_clean_db_free_space](../../relational-databases/system-stored-procedures/sp-clean-db-free-space-transact-sql.md) 저장 프로시저는 데이터베이스의 모든 파일을 정리 합니다.  
  
## <a name="permissions"></a>사용 권한  
 데이터베이스 역할의 멤버 자격이 필요 `db_owner` 합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `AdventureWorks2012` 데이터베이스의 주 데이터 파일에서 잔여 정보를 모두 정리하는 방법을 보여 줍니다.  
  
```sql  
USE master;  
GO  
EXEC sp_clean_db_file_free_space @dbname = N'AdventureWorks2012', @fileid = 1;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;저장 프로시저 데이터베이스 엔진](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [고스트 정리 프로세스 가이드](../ghost-record-cleanup-process-guide.md)    
 [sp_clean_db_free_space(Transact-SQL)](../../relational-databases/system-stored-procedures/sp-clean-db-free-space-transact-sql.md)
   
