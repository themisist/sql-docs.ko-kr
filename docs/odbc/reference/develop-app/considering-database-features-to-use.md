---
title: 사용할 데이터베이스 기능 고려 Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- interoperability [ODBC], database features
ms.assetid: 59760114-508e-46c5-81d2-8f2498c0d778
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a9d966781def1c3eab6a9568eab07ab591326171
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81299013"
---
# <a name="considering-database-features-to-use"></a>사용할 데이터베이스 기능 고려
기본 수준의 상호 운용성을 알고 나면 응용 프로그램에서 사용 하는 데이터베이스 기능을 고려해 야 합니다. 예를 들어 응용 프로그램에서 실행 하는 SQL 문은 무엇 인가요? 응용 프로그램에서 스크롤 가능 커서를 사용 하나요? 트랜잭션을? 절차? Long 데이터 모든 Dbms에서 지원 되지 않을 수 있는 기능에 대 한 자세한 내용은 [SQLGetInfo](../../../odbc/reference/syntax/sqlgetinfo-function.md), [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md)및 [SQLSetStmtAttr](../../../odbc/reference/syntax/sqlsetstmtattr-function.md) 함수 설명 및 [부록 C: SQL 문법을](../../../odbc/reference/appendixes/appendix-c-sql-grammar.md)참조 하세요. 응용 프로그램에 필요한 기능은 대상 Dbms 목록에서 일부 Dbms를 제거할 수 있습니다. 또한 응용 프로그램에서 많은 Dbms를 쉽게 대상으로 지정할 수 있습니다.  
  
 예를 들어 필요한 기능이 간단한 경우 일반적으로 높은 수준의 상호 운용성을 사용 하 여 구현할 수 있습니다. 간단한 **SELECT** 문을 실행 하 고 앞 으로만 이동 가능한 커서를 사용 하 여 결과를 검색 하는 응용 프로그램은 단순함: 거의 모든 드라이버와 dbms에서 필요한 기능을 지원 합니다.  
  
 그러나 스크롤할 수 있는 커서, 위치 지정 update 및 delete 문, 프로시저 등의 필요한 기능이 더 복잡 한 경우에는 종종 절충 해야 합니다. 다음과 같은 여러 가지 가능성이 있습니다.  
  
-   **더 낮은 상호 운용성, 기타 기능** 응용 프로그램은 기능을 포함 하지만 해당 기능을 지 원하는 Dbms 에서만 작동 합니다.  
  
-   **더 높은 상호 운용성, 더 작은 기능** 응용 프로그램은 기능을 삭제 하지만 Dbms를 사용 하 여 작동 합니다.  
  
-   **상호 운용성, 선택적 기능** 응용 프로그램은 기능을 포함 하지만 해당 기능을 지 원하는 Dbms 에서만 사용할 수 있도록 합니다.  
  
-   **더 높은 상호 운용성, 기타 기능** 응용 프로그램은이 기능을 지 원하는 Dbms에서 기능을 사용 하 고 그렇지 않은 Dbms에 대해 에뮬레이션 합니다.  
  
 처음 두 사례는 지원 되는 모든 Dbms에서 사용 되거나 none으로 사용 되기 때문에 구현 하기에 비교적 간단 합니다. 반면에 두 번째 경우는 더 복잡 합니다. 두 경우 모두 DBMS에서 기능을 지원 하는지 여부와 마지막 사례에서 이러한 기능을 에뮬레이트하는 잠재적으로 많은 양의 코드를 작성 해야 하는지 여부를 확인 해야 합니다. 따라서 이러한 스키마는 개발 시간이 더 많이 필요 하 고 런타임에 속도가 느릴 수 있습니다.  
  
 단일 데이터 원본에 연결할 수 있는 일반 쿼리 응용 프로그램을 고려해 보세요. 응용 프로그램은 사용자의 쿼리를 수락 하 고 결과를 창에 표시 합니다. 이제이 응용 프로그램에는 사용자가 여러 쿼리의 결과를 동시에 표시할 수 있도록 하는 하나의 기능이 있다고 가정 합니다. 즉, 쿼리를 실행 하 고 일부 결과를 확인 하 고 다른 쿼리를 실행 하 여 결과 중 일부를 확인 한 다음 첫 번째 쿼리로 돌아갈 수 있습니다. 일부 드라이버는 단일 활성 문만 지원 하기 때문에 상호 운용성 문제가 발생 합니다.  
  
 응용 프로그램은 **SQLGetInfo**에서 SQL_MAX_CONCURRENT_ACTIVITIES 옵션에 대해 드라이버가 반환 하는 항목에 따라 다양 한 옵션을 제공 합니다.  
  
-   **항상 여러 쿼리를 지원 합니다.** 드라이버에 연결한 후 응용 프로그램은 활성 문 수를 확인 합니다. 드라이버가 하나의 활성 문만 지 원하는 경우 응용 프로그램은 연결을 닫고 드라이버가 필요한 기능을 지원 하지 않는다는 것을 사용자에 게 알립니다. 응용 프로그램은 구현 하기 쉬우며 전체 기능이 있지만 상호 운용성이 낮습니다.  
  
-   **여러 쿼리를 지원 하지 않습니다.** 응용 프로그램은 기능을 모두 삭제 합니다. 구현 하기 쉬우며 상호 운용성이 낮지만 기능이 낮습니다.  
  
-   **드라이버가 수행 하는 경우에만 여러 쿼리를 지원 합니다.** 드라이버에 연결한 후 응용 프로그램은 활성 문 수를 확인 합니다. 응용 프로그램에서는 드라이버가 여러 활성 문을 지 원하는 경우에만 사용자가 이미 활성화 되어 있을 때 새 문을 시작할 수 있습니다. 응용 프로그램에는 더 높은 기능 및 상호 운용성이 있지만 구현 하기는 어렵습니다.  
  
-   **항상 여러 쿼리를 지원 하 고 필요한 경우 에뮬레이션 합니다.** 드라이버에 연결한 후 응용 프로그램은 활성 문 수를 확인 합니다. 응용 프로그램은 사용자가 이미 활성화 된 경우 항상 새 문을 시작할 수 있도록 허용 합니다. 드라이버가 하나의 활성 문만 지 원하는 경우 응용 프로그램은 해당 드라이버에 대 한 추가 연결을 열고 해당 연결에서 새 문을 실행 합니다. 응용 프로그램에는 전체 기능과 높은 수준의 상호 운용성이 있지만 구현 하기는 어렵습니다.
