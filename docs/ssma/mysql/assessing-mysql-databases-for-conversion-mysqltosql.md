---
title: 변환에 대 한 MySQL 데이터베이스 평가 (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Assessment reports
ms.assetid: 2a56a003-3b0f-453a-963c-00c9e40933ec
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 85923b0252eb24012c12e0c19937e076806b78bd
ms.sourcegitcommit: 777704aefa7e574f4b7d62ad2a4c1b10ca1731ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87823809"
---
# <a name="assessing-mysql-databases-for-conversion-mysqltosql"></a>변환을 위해 MySQL 데이터베이스 평가(MySQLToSQL)
개체를 로드 하 고 데이터를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 마이그레이션하기 전에 마이그레이션의 복잡성과 마이그레이션에 소요 되는 시간을 결정 해야 합니다. SSMA는 성공적으로 변환 되는 개체의 비율을 보여 주는 평가 보고서를 만들 수 있습니다. SSMA를 사용 하면 변환 오류를 발생 시키는 특정 문제를 확인할 수도 있습니다.  
  
## <a name="creating-assessment-reports"></a>평가 보고서 만들기  
이 평가 보고서를 만들 때 SSMA는 선택한 MySQL 데이터베이스 개체를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 구문으로 변환한 다음 결과를 표시 합니다.  
  
**평가 보고서를 만들려면**  
  
1.  MySQL 메타 데이터 탐색기에서 평가할 스키마를 선택 합니다.  
  
2.  개별 개체를 생략 하려면 해당 개체 옆에 있는 확인란의 선택을 취소 합니다.  
  
3.  **스키마**를 마우스 오른쪽 단추로 클릭 한 다음 **보고서 만들기**를 선택 합니다.  
  
    개체를 마우스 오른쪽 단추로 클릭 하 여 개별 개체를 분석 합니다. 그런 다음 **보고서 만들기**를 선택 합니다.  
  
    SSMA는 창의 아래쪽에 있는 상태 표시줄에 진행률을 표시 합니다. 출력 창이 표시 되 면 출력 창에도 메시지가 표시 됩니다.  
  
    평가가 완료 되 면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] MySQL에 대 한 Migration Assistant 평가 보고서 창이 표시 됩니다.  
  
## <a name="using-assessment-reports"></a>평가 보고서 사용  
평가 보고서 창에는 다음과 같은 세 개의 창이 있습니다.  
  
-   왼쪽 창에는 평가 보고서에 포함 된 개체의 계층 구조가 포함 되어 있습니다. 계층 구조를 찾아보고 개체 및 개체 범주를 선택 하 여 변환 통계 및 코드를 볼 수 있습니다.  
  
-   오른쪽 창의 내용은 왼쪽 창에서 선택한 항목에 따라 달라 집니다.  
  
    스키마와 같은 개체 그룹을 선택한 경우 오른쪽 창에는 변환 통계 창과 범주별 개체 창이 포함 됩니다. 변환 통계 창에는 선택한 개체에 대 한 변환 통계가 표시 됩니다. 범주별 개체 창에는 개체 또는 개체 범주에 대 한 변환 통계가 표시 됩니다.  
  
    함수, 프로시저, 테이블 또는 뷰를 선택 하면 오른쪽 창에 통계, 소스 코드 및 대상 코드가 포함 됩니다.  
  
    -   위쪽 영역에는 개체에 대 한 전체 통계가 표시 됩니다. 이 정보를 보려면 **통계** 를 확장 해야 할 수 있습니다.  
  
    -   소스 영역에는 왼쪽 창에서 선택한 개체의 소스 코드가 표시 됩니다. 강조 표시 된 영역에는 문제가 있는 소스 코드가 표시 됩니다.  
  
    -   대상 영역에는 변환 된 코드가 표시 됩니다. 빨간색 텍스트는 문제가 있는 코드 및 오류 메시지를 표시 합니다.  
  
-   아래쪽 창에는 메시지 번호로 그룹화 된 변환 메시지가 표시 됩니다. **오류**, **경고**또는 **정보** 를 클릭 하 여 메시지 범주를 확인 한 다음 메시지 그룹을 확장할 수 있습니다. 개별 메시지를 클릭 하 여 왼쪽 창에서 개체를 선택 하 고 오른쪽 창에 세부 정보를 표시 합니다.  
  
## <a name="analyzing-conversion-problems-by-using-the-assessment-report"></a>평가 보고서를 사용 하 여 변환 문제 분석  
변환 통계 창에는 변환 통계가 표시 됩니다. 범주에 대 한 백분율이 100% 미만이 면 변환에 성공 하지 못한 이유를 확인 해야 합니다.  
  
**변환 문제를 확인 하려면**  
  
1.  이전 절차의 지침을 사용 하 여 평가 보고서를 만듭니다.  
  
2.  왼쪽 창에서 빨간색 오류 아이콘이 있는 스키마 또는 폴더를 확장 합니다. 변환에 실패 한 개별 항목을 선택할 때까지 항목을 계속 확장 합니다.  
  
3.  원본 창 위쪽에서 **다음 문제**를 클릭 합니다.  
  
    대상 탐색 창의 관련 코드와 마찬가지로 문제가 있는 코드가 강조 표시 됩니다.  
  
4.  오류 메시지를 검토 한 다음 변환 문제를 일으킨 개체를 사용 하 여 수행할 작업을 결정 합니다.  
  
-   SSMA에서 MySQL 구문을 업데이트 합니다. 프로시저 및 함수에 대 한 구문도 업데이트할 수 있습니다. 구문을 업데이트 하려면 MySQL 메타 데이터 탐색기 창에서 개체를 선택 하 고 **sql** 탭을 클릭 한 다음 sql 코드를 수정 합니다. 항목에서 벗어나면 업데이트 된 구문을 저장 하 라는 메시지가 표시 됩니다. **보고서** 탭에서 개체에 대 한 보고 된 오류를 볼 수 있습니다.  
  
-   MySQL에서 MySQL 개체를 수정 하 여 문제가 있는 코드를 제거 하거나 수정할 수 있습니다. 업데이트 된 코드를 SSMA에 로드 하려면 메타 데이터를 업데이트 해야 합니다. 자세한 내용은 [MySQL에 연결 &#40;MySQLToSQL&#41;](../../ssma/mysql/connecting-to-mysql-mysqltosql.md)을 참조 하세요.  
  
-   마이그레이션할 때 개체를 제외할 수 있습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]또는 SQL Azure 메타 데이터 탐색기 및 Mysql 메타 데이터 탐색기에서 개체를로 로드 하기 전에 항목 옆에 있는 확인란의 선택을 취소 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 하거나 mysql에서 데이터를 SQL Azure 하 고 마이그레이션합니다.  
  
## <a name="next-step"></a>다음 단계  
[MySQL 데이터베이스 &#40;MySQLToSQL&#41;변환](../../ssma/mysql/converting-mysql-databases-mysqltosql.md)  
  
## <a name="see-also"></a>참고 항목  
[MySQL 데이터베이스를 SQL Server-Azure SQL Database &#40;MySQLToSql&#41;로 마이그레이션](../../ssma/mysql/migrating-mysql-databases-to-sql-server-azure-sql-db-mysqltosql.md)  
  
