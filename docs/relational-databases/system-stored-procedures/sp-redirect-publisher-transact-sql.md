---
title: sp_redirect_publisher (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_redirect_publisher_TSQL
- sp_redirect_publisher
helpviewer_keywords:
- sp_redirect_publisher
ms.assetid: af45e2b2-57fb-4bcd-a58b-e61401fb3b26
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 54a53c3e1678215ad2eb1410a00da4904d0f84e7
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85734307"
---
# <a name="sp_redirect_publisher-transact-sql"></a>sp_redirect_publisher(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  기존 게시자/데이터베이스 쌍에 대한 리디렉션된 게시자를 지정합니다. 게시자 데이터베이스가 Always On 가용성 그룹에 속하는 경우 리디렉션된 게시자는 가용성 그룹에 연결 된 가용성 그룹 수신기 이름입니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_redirect_publisher   
    [ @original_publisher = ] 'original_publisher',  
    [ @publisher_db = ] 'database_name'   
    [ , [ @redirected_publisher = ] 'new_publisher' ]  
```  
  
## <a name="arguments"></a>인수  
`[ @original_publisher = ] 'original_publisher'`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]원래 데이터베이스를 게시 한 인스턴스의 이름입니다. *original_publisher* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @publisher_db = ] 'publisher_db'`게시 되는 데이터베이스의 이름입니다. *publisher_db* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @redirected_publisher = ] 'redirected_publisher'`새 게시자가 될 가용성 그룹에 연결 된 가용성 그룹 수신기 이름입니다. *redirected_publisher* 는 **sysname**이며 기본값은 없습니다. 가용성 그룹 수신기를 기본 포트가 아닌 다른 포트로 구성한 경우 `'Listenername,51433'`과 같이 포트 번호를 수신기 이름과 함께 지정합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 None  
  
## <a name="remarks"></a>설명  
 **sp_redirect_publisher** 를 사용 하 여 게시자/데이터베이스 쌍을 가용성 그룹의 수신기와 연결 하 여 복제 게시자를 Always On 가용성 그룹의 현재 주 복제본으로 리디렉션할 수 있습니다. 게시 된 데이터베이스를 포함 하는 가용성 그룹에 대해 AG 수신기를 구성한 후 **sp_redirect_publisher** 를 실행 합니다.  
  
 원래 게시자의 게시 데이터베이스가 주 복제본의 가용성 그룹에서 제거 된 경우 * \@ redirected_publisher* 매개 변수의 값을 지정 하지 않고 **sp_redirect_publisher** 을 실행 하 여 게시자/데이터베이스 쌍에 대 한 리디렉션을 제거 합니다. 에서 게시자를 리디렉션하는 방법에 대 한 자세한 내용은 [SQL Server&#41;&#40;AlwaysOn 게시 데이터베이스 유지 관리 ](../../database-engine/availability-groups/windows/maintaining-an-always-on-publication-database-sql-server.md)를 참조 하세요.  
  
## <a name="permissions"></a>사용 권한  
 호출자는 **sysadmin** 고정 서버 역할의 멤버 이거나 배포 데이터베이스에 대 한 **db_owner** 고정 데이터베이스 역할의 멤버 이거나 게시자 데이터베이스에 연결 된 정의 된 게시에 대 한 게시 액세스 목록의 멤버 여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;를 &#40;하는 복제 저장 프로시저](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;sp_validate_redirected_publisher &#40;](../../relational-databases/system-stored-procedures/sp-validate-redirected-publisher-transact-sql.md)   
 [Transact-sql&#41;sp_get_redirected_publisher &#40;](../../relational-databases/system-stored-procedures/sp-get-redirected-publisher-transact-sql.md)   
 [Transact-sql&#41;sp_validate_replica_hosts_as_publishers &#40;](../../relational-databases/system-stored-procedures/sp-validate-replica-hosts-as-publishers-transact-sql.md)  
  
  
