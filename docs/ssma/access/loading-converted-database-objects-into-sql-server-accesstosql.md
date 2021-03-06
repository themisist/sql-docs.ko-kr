---
title: 변환 된 데이터베이스 개체를 SQL Server로 로드 하는 중 (AccessToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Access databases, loading converted objects into SQL Azure
- Access databases, loading converted objects into SQL Server
- data, securing
- loading objects into SQL Azure
- loading objects into SQL Server
- migrating objects into SQL Azure
- migrating objects into SQL Server
- moving objects into SQL Azure
- moving objects into SQL Server
- schemas, loading into SQL Azure
- schemas, loading into SQL Server
- scripting converted objects
- securing data
- SQL Azure, loading objects into
- SQL Server, loading objects into
- synchronizing metadata with SQL Azure
- synchronizing metadata with SQL Server
- uploading objects into SQL Azure
- uploading objects into SQL Server
ms.assetid: 4e854eee-b10c-4f0b-9d9e-d92416e6f2ba
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 7effaa973b7a39df6fc0b9385a5cfde4fdad18d4
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "67986315"
---
# <a name="loading-converted-database-objects-into-sql-server-accesstosql"></a>변환 된 데이터베이스 개체를 SQL Server (AccessToSQL)로 로드 하는 중
Access 데이터베이스 개체를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure로 변환한 후에는 결과 데이터베이스 개체를 또는 SQL Azure에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로드할 수 있습니다. SSMA에서 개체를 만들거나 개체를 스크립팅 하 고 스크립트를 직접 실행할 수 있습니다. 또한 SSMA를 사용 하면 또는 SQL Azure 데이터베이스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 실제 콘텐츠를 사용 하 여 대상 메타 데이터를 업데이트할 수 있습니다.  
  
## <a name="choosing-between-synchronization-and-scripts"></a>동기화 및 스크립트 중에서 선택  
변환 된 데이터베이스 개체를 수정 하지 않고에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로드 하거나 수정 하지 않고 SQL Azure 하려면 ssma에서 직접 데이터베이스 개체를 만들거나 다시 만들 수 있습니다. 이 방법은 쉽고 간단 하지만 저장 프로시저를 제외 하 고 [!INCLUDE[tsql](../../includes/tsql-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 개체를 정의 하는 코드를 사용자 지정할 수 없습니다.  
  
개체를 만드는 데 사용 되 [!INCLUDE[tsql](../../includes/tsql-md.md)] 는을 수정 하려는 경우 또는 개체 생성을 보다 세부적으로 제어 하려는 경우 ssma를 사용 하 여 스크립트를 만듭니다. 그런 다음 해당 스크립트를 수정 하 고, 각 개체를 개별적으로 만들고 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , 에이전트를 사용 하 여 해당 개체 만들기를 예약할 수 있습니다.  
  
## <a name="using-ssma-to-synchronize-objects-with-sql-server"></a>SSMA를 사용 하 여 SQL Server와 개체 동기화  
SSMA를 사용 하 여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스 개체를 만들거나 SQL Azure 하려면 다음 절차에서와 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 같이 또는 SQL Azure 메타 데이터 탐색기에서 개체를 선택한 다음 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 개체를 동기화 합니다. 기본적으로 또는 SQL Azure에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체가 이미 있거나 ssma 메타 데이터에 일부 로컬 변경 내용이 있거나 해당 개체의 정의에 대 한 업데이트가 있는 경우 ssma는 또는 SQL Azure에서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체 정의를 변경 합니다. **프로젝트 설정을**편집 하 여 기본 동작을 변경할 수 있습니다.  
  
> [!NOTE]  
> Access 데이터베이스에서 변환 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 되지 않은 기존 또는 SQL Azure 데이터베이스 개체를 선택할 수 있습니다. 그러나 SSMA는 이러한 개체를 다시 만들거나 변경 하지 않습니다.  
  
**SQL Server 또는 SQL Azure를 사용 하 여 개체를 동기화 하려면**  
  
1.  또는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL Azure Metadata 탐색기에서 top [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 노드를 확장 한 다음 **데이터베이스**를 확장 합니다.  
  
2.  처리할 개체를 선택 하십시오.  
  
    -   전체 데이터베이스를 동기화 하려면 데이터베이스 이름 옆의 확인란을 선택 합니다.  
  
    -   개별 개체 또는 개체의 범주를 동기화 하거나 생략 하려면 개체 또는 폴더 옆의 확인란을 선택 하거나 선택 취소 합니다.  
  
3.  또는 SQL Azure 메타 데이터 탐색기에서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 처리할 개체를 선택한 후 데이터베이스를 마우스 오른쪽 단추로 클릭 **하**고 **데이터베이스와 동기화**를 클릭 합니다.  
  
    개체 또는 해당 부모 폴더를 마우스 오른쪽 단추로 클릭 한 다음 **데이터베이스와 동기화**를 클릭 하 여 개별 개체 또는 개체 범주를 동기화 할 수도 있습니다.  
  
    그런 다음, SSMA는 두 개의 항목 그룹을 볼 수 있는 **데이터베이스와 동기화** 대화 상자를 표시 합니다. 왼쪽에서 SSMA는 트리로 표시 되는 선택한 데이터베이스 개체를 표시 합니다. 오른쪽에서 SSMA 메타 데이터의 동일한 개체를 나타내는 트리를 볼 수 있습니다. 오른쪽 또는 왼쪽 ' + ' 단추를 클릭 하 여 트리를 확장할 수 있습니다. 동기화 방향은 두 트리 사이에 배치 된 작업 열에 표시 됩니다.  
  
    작업 기호는 다음 세 가지 상태일 수 있습니다.  
  
    -   왼쪽 화살표는 메타 데이터의 내용이 데이터베이스에 저장 된다는 것을 의미 합니다 (기본값).  
  
    -   오른쪽 화살표는 데이터베이스 콘텐츠가 SSMA 메타 데이터를 덮어쓰는 것을 의미 합니다.  
  
    -   크로스 기호는 아무런 조치도 취할 수 없음을 의미 합니다.  
  
    작업 기호를 클릭 하 여 상태를 변경 합니다. **데이터베이스와 동기화** 대화 상자에서 **확인** 단추를 클릭 하면 실제 동기화가 수행 됩니다.  
  
## <a name="scripting-objects"></a>개체 스크립팅  
변환 된 데이터베이스 개체의 [!INCLUDE[tsql](../../includes/tsql-md.md)] 정의를 저장 하거나 개체 정의를 변경 하 고 스크립트를 직접 실행 하려는 경우 변환 된 데이터베이스 개체 정의를 스크립트에 [!INCLUDE[tsql](../../includes/tsql-md.md)] 저장할 수 있습니다.  
  
**하나 이상의 개체를 스크립트에 저장 하려면**  
  
1.  메타 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 탐색기에서 최상위 노드 (서버 이름)를 확장 한 다음 **데이터베이스**를 확장 합니다.  
  
2.  다음 중 하나 이상을 수행합니다.  
  
    -   전체 데이터베이스를 스크립팅 하려면 데이터베이스 이름 옆의 확인란을 선택 합니다.  
  
    -   개별 뷰를 스크립팅 하거나 생략 하려면 데이터베이스를 확장 하 고 **보기**를 확장 한 다음 보기 옆의 확인란을 선택 하거나 선택 취소 합니다.  
  
    -   개별 테이블을 스크립팅 하거나 생략 하려면 데이터베이스를 확장 하 고 **테이블**을 확장 한 다음 테이블 옆의 확인란을 선택 하거나 선택 취소 합니다.  
  
    -   테이블에 대 한 개별 인덱스를 스크립팅 하거나 생략 하려면 테이블을 확장 하 고 **인덱스**를 확장 한 다음 인덱스를 선택 하거나 선택 취소 합니다.  
  
3.  **데이터베이스** 를 마우스 오른쪽 단추로 클릭 하 고 **스크립트로 저장**을 선택 합니다.  
  
    개별 개체를 스크립팅할 수도 있습니다. 개체를 스크립팅하려면 선택 된 개체에 관계 없이 개체를 마우스 오른쪽 단추로 클릭 하 고 **스크립트로 저장**을 선택 합니다.  
  
4.  다른 이름 **으로 저장** 대화 상자에서 스크립트를 저장할 폴더를 찾은 다음 **파일 이름** 상자에 파일 이름을 입력 하 고 **확인**을 클릭 합니다.  
  
    SSMA는 .sql 파일 이름 확장명을 추가 합니다.  
  
### <a name="modifying-scripts"></a>스크립트 수정  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 개체 정의를 스크립트로 저장 한 후에는를 사용 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 하 여 스크립트를 수정할 수 있습니다.  
  
**스크립트를 수정 하려면**  
  
1.  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **파일** 메뉴에서 **열기**를 가리킨 다음 **파일**을 클릭합니다.  
  
2.  **열기** 대화 상자에서 스크립트 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.  
  
3.  쿼리 편집기를 사용 하 여 스크립트 파일을 편집 합니다.  
  
    쿼리 편집기에 대 한 자세한 내용은 온라인 설명서의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "편집기의 편리한 명령 및 기능"을 참조 하십시오.  
  
4.  스크립트를 저장 하려면 파일 메뉴에서 **저장**을 선택 합니다.  
  
### <a name="running-scripts"></a>스크립트 실행  
에서 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]스크립트나 개별 문을 실행할 수 있습니다.  
  
**스크립트를 실행하려면**  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **파일** 메뉴에서 **열기** 를 가리킨 다음 **파일**을 클릭 합니다.  
  
2.  **열기** 대화 상자에서 스크립트 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.  
  
3.  전체 스크립트를 실행 하려면 **f5** 키를 누릅니다.  
  
4.  문 집합을 실행 하려면 쿼리 편집기 창에서 문을 선택 하 고 **f5** 키를 누릅니다.  
  
쿼리 편집기를 사용 하 여 스크립트를 실행 하는 방법에 대 한 자세한 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] 내용은 온라인 설명서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 의 "쿼리"를 참조 하십시오.  
  
**Sqlcmd** 유틸리티 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트를 사용 하 여 명령줄에서 스크립트를 실행할 수도 있습니다. **Sqlcmd**에 대 한 자세한 내용은 온라인 설명서의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "sqlcmd 유틸리티"를 참조 하십시오. 에이전트에 대 한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 자세한 내용은 온라인 설명서의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "관리 태스크 자동화 (에이전트)"를 참조 하십시오.  
  
## <a name="securing-objects-in-sql-server"></a>SQL Server에서 개체 보안  
변환 된 데이터베이스 개체를에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]로드 한 후에는 해당 개체에 대 한 사용 권한을 부여 하 고 거부할 수 있습니다. 로 데이터를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]마이그레이션하기 전에이 작업을 수행 하는 것이 좋습니다. 에서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]개체를 보호 하는 방법에 대 한 자세한 내용은 온라인 설명서의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] "데이터베이스 및 데이터베이스 응용 프로그램에 대 한 보안 고려 사항"을 참조 하십시오.  
  
## <a name="next-step"></a>다음 단계  
마이그레이션 프로세스의 다음 단계에서는 [데이터를 SQL Server으로 마이그레이션합니다](migrating-access-data-into-sql-server-azure-sql-db-accesstosql.md).  
  
## <a name="see-also"></a>참고 항목  
[SQL Server로 Access 데이터베이스 마이그레이션](migrating-access-databases-to-sql-server-azure-sql-db-accesstosql.md)  
  
