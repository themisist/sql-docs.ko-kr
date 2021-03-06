---
title: 추적 템플릿 만들기
titleSuffix: SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.openlocfilehash: 2944e21afee17f66eef51723f4e552c947f43db8
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "75307315"
---
# <a name="create-a-trace-template-sql-server-profiler"></a>추적 템플릿 만들기(SQL Server Profiler)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  이 항목에서는 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]을 사용하여 새 추적 템플릿을 만드는 방법에 대해 설명합니다.  
  
### <a name="to-create-a-trace-template"></a>추적 템플릿을 만들려면  
  
1.  **파일** 메뉴에서 **템플릿**을 가리킨 다음 **새 템플릿**을 클릭합니다.  
  
2.  **추적 템플릿 속성** 대화 상자의 **서버 유형 선택**목록에서 서버 유형을 선택합니다.  
  
3.  **새 템플릿 이름** 상자에 템플릿 이름을 입력합니다.  
  
4.  필요에 따라 **기존 템플릿에서 새 템플릿 만들기**를 클릭한 다음 목록에서 템플릿을 선택합니다.  
  
     모든 이벤트, 데이터 열 및 필터는 처음에 선택한 템플릿에서 지정한 대로 설정됩니다.  
  
5.  필요에 따라 **선택한 서버 유형에 대한 기본 템플릿으로 사용**을 클릭합니다.  
  
6.  **이벤트 선택** 탭에서 이벤트, 데이터 열 또는 필터를 추가, 제거 또는 수정합니다.  
  
7.  **이벤트 선택**탭에서 표 형태 컨트롤을 사용하여 다음과 같이 추적 파일에서 이벤트와 데이터 열을 추가하거나 제거할 수 있습니다.  
  
    -   이벤트를 추가하려면 **이벤트** 열의 해당 이벤트 범주를 확장한 다음 이벤트 이름을 선택합니다.  
  
    -   이벤트를 추가할 때는 관련된 모든 데이터 열이 기본적으로 포함됩니다. 추적에서 이벤트에 대한 데이터 열을 제거하려면 해당 이벤트에 대한 데이터 열의 확인란 선택을 취소합니다.  
  
    -   필터를 추가하려면 데이터 열 이름을 클릭하고 **필터 편집** 대화 상자에 필터 조건을 지정합니다. 또한 데이터 열 이름을 마우스 오른쪽 단추로 클릭하고 **열 필터 편집** 을 클릭하여 **필터 편집** 대화 상자를 실행할 수 있습니다. **확인** 을 클릭하여 필터를 추가합니다.  
  
8.  **저장**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적 파일에 대해 이벤트 및 데이터 열 지정&#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)   
 [실행 중인 추적으로부터 템플릿 파생&#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)   
 [추적 파일 또는 추적 테이블에서 템플릿 파생&#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)   
 [SQL Server Profiler 템플릿 및 권한](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
