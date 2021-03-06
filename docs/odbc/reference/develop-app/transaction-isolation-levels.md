---
title: 트랜잭션 격리 수준 (ODBC) | Microsoft Docs
ms.custom: seo-dt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- dirty reads [ODBC]
- isolation levels [ODBC]
- nonrepeatable reads [ODBC]
- read uncommitted [ODBC]
- read committed [ODBC]
- serializable reads [ODBC]
- phantoms [ODBC]
- transaction isolation [ODBC]
- repeatable reads [ODBC]
- transactions [ODBC], isolation
ms.assetid: 0d638d55-ffd0-48fb-834b-406f466214d4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 622b4cd7f0db259b5ecfd5be63b27df64be965e7
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81298036"
---
# <a name="transaction-isolation-levels-odbc"></a>트랜잭션 격리 수준 (ODBC)
*트랜잭션 격리 수준은* 트랜잭션 격리가 성공 하는 정도를 측정 한 것입니다. 특히 트랜잭션 격리 수준은 다음 현상 있는지 여부에 따라 정의 됩니다.  
  
-   **더티 읽기** 커밋되지 않은 *읽기* 는 트랜잭션이 아직 커밋되지 않은 데이터를 읽을 때 발생 합니다. 예를 들어 트랜잭션 1에서 행을 업데이트 한다고 가정 합니다. 트랜잭션 1이 업데이트를 커밋하기 전에 트랜잭션 2가 업데이트 된 행을 읽습니다. 트랜잭션 1이 변경 내용을 롤백하는 경우 트랜잭션 2에는 존재 하지 않는 것으로 간주 되는 읽기 데이터가 있습니다.  
  
-   **반복할 읽기** *반복할 읽기* 는 트랜잭션이 동일한 행을 두 번 읽을 때 발생 하지만 매번 다른 데이터를 가져옵니다. 예를 들어 트랜잭션 1에서 행을 읽는 경우를 가정 합니다. 트랜잭션 2가 해당 행을 업데이트 하거나 삭제 하 고 업데이트 또는 삭제를 커밋합니다. 트랜잭션 1이 행을 다시 읽습니다 다른 행 값을 검색 하거나 행이 삭제 되었음을 검색 합니다.  
  
-   **Phantoms** *가상* 은 검색 조건과 일치 하지만 처음에는 표시 되지 않는 행입니다. 예를 들어 트랜잭션 1이 일부 검색 조건을 충족 하는 행 집합을 읽는 경우 트랜잭션 2는 트랜잭션 1에 대 한 검색 조건과 일치 하는 새 행 (업데이트 또는 삽입을 통해)을 생성 합니다. 트랜잭션 1이 행을 읽는 문을 다시 실행 하면 다른 행 집합을 가져옵니다.  
  
 4 개의 트랜잭션 격리 수준 (SQL-92에 정의 됨)은 이러한 현상 측면에서 정의 됩니다. 다음 표에서 "X"는 발생할 수 있는 각 현상을 표시 합니다.  
  
|트랜잭션 격리 수준|더티 읽기|반복할 읽기|Phantoms|  
|---------------------------------|-----------------|-------------------------|--------------|  
|커밋되지 않은 읽기|X|X|X|  
|커밋된 읽기|--|X|X|  
|반복 읽기|--|--|X|  
|직렬화 가능|--|--|--|  
  
 다음 표에서는 DBMS에서 트랜잭션 격리 수준을 구현할 수 있는 간단한 방법을 설명 합니다.  
  
> [!IMPORTANT]  
>  대부분의 Dbms에서는 동시성을 향상 시키기 위해 보다 복잡 한 스키마를 사용 합니다. 이러한 예제는 설명을 위해 제공 된 용도로만 제공 됩니다. 특히 ODBC는 특정 Dbms에서 트랜잭션을 분리 하는 방법을 규정 하지 않습니다.  
  
|트랜잭션 격리|가능한 구현|  
|---------------------------|-----------------------------|  
|커밋되지 않은 읽기|트랜잭션은 서로 격리 되지 않습니다. DBMS에서 다른 트랜잭션 격리 수준을 지 원하는 경우 해당 수준을 구현 하는 데 사용 하는 모든 메커니즘을 무시 합니다. 다른 트랜잭션에 부정적인 영향을 주지 않도록 읽기 커밋되지 않은 읽기 수준에서 실행 중인 트랜잭션은 일반적으로 읽기 전용입니다.|  
|커밋된 읽기|트랜잭션은 다른 트랜잭션에 의해 쓰기 잠금이 해제 될 때까지 대기 합니다. 이렇게 하면 "더티" 데이터를 읽을 수 없습니다.<br /><br /> 트랜잭션은 현재 행에 대 한 읽기 잠금 (행을 읽기만 하는 경우) 또는 쓰기 잠금 (행을 업데이트 하거나 삭제 하는 경우)을 유지 하 여 다른 트랜잭션이 업데이트 또는 삭제 되지 않도록 합니다. 트랜잭션은 현재 행에서 이동 하면 읽기 잠금을 해제 합니다. 커밋 또는 롤백될 때까지 쓰기 잠금을 보유 합니다.|  
|반복 읽기|트랜잭션은 다른 트랜잭션에 의해 쓰기 잠금이 해제 될 때까지 대기 합니다. 이렇게 하면 "더티" 데이터를 읽을 수 없습니다.<br /><br /> 트랜잭션은 응용 프로그램에 반환 하는 모든 행에 대 한 읽기 잠금을 보유 하 고 삽입, 업데이트 또는 삭제 하는 모든 행에 대 한 잠금을 작성 합니다. 예를 들어 트랜잭션에 SQL 문 ** \* SELECT FROM Orders**가 포함 되어 있는 경우, 트랜잭션은 응용 프로그램에서이를 인출 하는 행을 읽습니다. 트랜잭션에 SQL 문 **DELETE FROM Orders FROM Status = ' CLOSED '** 가 포함 된 경우 트랜잭션은 행을 삭제 하는 동안 행을 기록 합니다.<br /><br /> 다른 트랜잭션은 이러한 행을 업데이트 하거나 삭제할 수 없으므로 현재 트랜잭션은 반복할 읽기를 방지 합니다. 트랜잭션은 커밋되거나 롤백될 때 잠금을 해제 합니다.|  
|직렬화 가능|트랜잭션은 다른 트랜잭션에 의해 쓰기 잠금이 해제 될 때까지 대기 합니다. 이렇게 하면 "더티" 데이터를 읽을 수 없습니다.<br /><br /> 트랜잭션은 영향을 받는 행 범위에서 읽기 잠금 (행을 읽기만 하는 경우) 또는 쓰기 잠금 (행을 업데이트 하거나 삭제할 수 있는 경우)을 유지 합니다. 예를 들어 트랜잭션에 SQL 문 ** \* SELECT FROM orders**가 포함 되어 있으면 범위는 전체 orders 테이블입니다. 트랜잭션은 테이블을 읽고 잠그고 새 행을 삽입 하는 것을 허용 하지 않습니다. **상태 = ' 닫힘 ' 인 ORDERS에서**SQL 문 삭제를 포함 하는 트랜잭션이 있는 경우 해당 범위는 "Closed" 상태의 모든 행입니다. 트랜잭션 쓰기는 Orders 테이블에서 상태가 "닫힘" 인 모든 행을 잠그고 결과 행의 상태가 "닫힘"이 되도록 행을 삽입 하거나 업데이트할 수 없습니다.<br /><br /> 다른 트랜잭션은 범위에서 행을 업데이트 하거나 삭제할 수 없으므로 현재 트랜잭션은 반복할 읽기를 방지 합니다. 다른 트랜잭션은 범위에 행을 삽입할 수 없기 때문에 현재 트랜잭션은 모든 phantoms을 방지 합니다. 트랜잭션은 커밋되거나 롤백될 때 잠금을 해제 합니다.|  
  
 트랜잭션 격리 수준은 자체 변경 내용을 확인 하는 트랜잭션의 기능에 영향을 주지 않는다는 점에 유의 해야 합니다. 트랜잭션은 항상 변경 내용을 볼 수 있습니다. 예를 들어 트랜잭션은 두 개의 **UPDATE** 문으로 구성 될 수 있으며, 첫 번째는 모든 직원의 급여를 10%로, 두 번째는 모든 직원의 급여를 해당 금액으로 설정 합니다. 이는 두 번째 **UPDATE** 문이 첫 번째의 결과를 볼 수 있기 때문에 단일 트랜잭션으로 성공 합니다.
