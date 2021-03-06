---
title: Modify a SQL Server Agent Proxy
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 06/03/2020
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 1bb6ebd0f62531fc84c953e8326d3d16a75586d2
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85715778"
---
# <a name="modify-a-sql-server-agent-proxy"></a>Modify a SQL Server Agent Proxy

[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> 현재 [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)에서 일부 SQL Server 에이전트 기능이 지원됩니다. 자세한 내용은 [SQL Server에서 Azure SQL Database Managed Instance T-SQL 차이점](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)을 참조하세요.

이 문서에서는 [!INCLUDE[msCoName](../../includes/msconame_md.md)] 또는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]을 사용하여 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]에서 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] 에이전트 프록시를 수정하는 방법에 대해 설명합니다.  

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>시작하기 전 주의 사항  
  
### <a name="limitations-and-restrictions"></a><a name="Restrictions"></a>제한 사항  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 프록시는 자격 증명을 사용하여 Windows 사용자 계정에 대한 정보를 저장합니다. 자격 증명에 지정된 사용자에게 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 가 실행 중인 컴퓨터에 대한 "일괄 작업으로 로그온" 권한이 있어야 합니다.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트는 프록시에 대한 하위 시스템 액세스 권한을 확인하고 작업 단계가 실행될 때마다 프록시에 대한 액세스 권한을 부여합니다. 프록시에 하위 시스템에 대한 액세스 권한이 없으면 작업 단계가 실패합니다. 그렇지 않으면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트가 프록시에 지정된 사용자를 가장하여 작업 단계를 실행합니다.  
  
-   사용자의 로그인에 프록시에 대한 액세스 권한이 있거나 사용자가 프록시에 대한 액세스 권한이 있는 역할에 속하는 경우 해당 사용자는 작업 단계에서 프록시를 사용할 수 있습니다.  
  
### <a name="security"></a><a name="Security"></a>보안  
  
#### <a name="permissions"></a><a name="Permissions"></a>권한  
**sysadmin** 고정 서버 역할의 멤버만 프록시 계정을 만들거나 수정하거나 삭제할 수 있습니다.  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>SQL Server Management Studio 사용  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a>[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 프록시를 수정하려면  
  
1.  **개체 탐색기**에서 더하기 기호를 클릭하여 수정하려는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 프록시 계정이 포함된 서버를 확장합니다.  
  
2.  더하기 기호를 클릭하여 **SQL Server 에이전트**를 확장합니다.  
  
3.  더하기 기호를 클릭하여 **프록시** 폴더를 확장합니다.  
  
4.  더하기 기호를 클릭하여 프록시에 대한 하위 시스템 노드(예: **ActiveX 스크립트**)를 확장합니다.  
  
5.  수정하려는 프록시 계정을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
6.  _proxy\_name_**프록시 계정 속성** 대화 상자에서 필요에 따라 프록시 계정을 변경합니다. 이 대화 상자의 옵션에 대한 자세한 내용은 [SQL Server 에이전트 프록시 만들기](../../ssms/agent/create-a-sql-server-agent-proxy.md)를 참조하세요.  
  
7.  완료되었으면 **확인**을 클릭합니다.  
  
## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a>Transact-SQL 사용  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a>[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 프록시를 수정하려면  
  
1.  **개체 탐색기**에서 [!INCLUDE[ssDE](../../includes/ssde_md.md)]인스턴스에 연결합니다.  
  
2.  표준 도구 모음에서 **새 쿼리**를 클릭합니다.  
  
3.  다음 예를 복사하여 쿼리 창에 붙여 넣고 **실행**을 클릭합니다.  
  
    ```sql
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
자세한 내용은 [sp_update_proxy(Transact-SQL)](https://msdn.microsoft.com/864fd0e6-9d61-4f07-92ef-145318d2f881)를 참조하세요.  
  
