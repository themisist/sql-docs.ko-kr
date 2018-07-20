---
title: '방법: 코드 조각 개요 표시 및 Transact-SQL 스크립트에 코드 조각 추가 | Microsoft Docs'
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 543e7ce7-8639-4281-8a91-85314755e5de
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9b08337c4602e7eaad2da376b22caa8f806e5b18
ms.sourcegitcommit: 2f07d285824a8982c279f3816b220e61a2d91b06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37094619"
---
# <a name="how-to-outline-and-add-snippets-to-transact-sql-script"></a>방법: 코드 조각 개요 표시 및 Transact-SQL 스크립트에 코드 조각 추가
SQL Server Data Tools에는 응용 프로그램에 바로 삽입할 수 있는 코드 조각으로 구성된 코드 라이브러리가 포함되어 있습니다. 각 코드 조각은 함수, 테이블, 트리거, 인덱스, 뷰, 사용자 정의 데이터 형식 등을 만드는 것과 같은 완전한 스크립팅 작업을 수행합니다. 마우스 클릭 몇 번만으로도 소스 코드에 코드 조각을 삽입할 수 있습니다. 이러한 코드 조각은 입력에 소비되는 시간을 줄여 생산성을 높여 줍니다.  
  
적절한 코드 조각을 찾아보기 위해 필요한 경우 선택 가능한 코드 조각의 범주화된 목록을 제공하는 코드 조각 선택기를 사용할 수 있습니다. 코드에 코드 조각을 추가한 후에는 변수 이름을 보다 적절한 이름으로 바꾸거나 코드 조각을 저장 프로시저의 실제 논리에 배치하는 등의 사용자 지정 작업이 필요한 부분이 있을 수 있습니다. 이를 쉽게 구별하기 위해 삽입된 조각 코드에는 하나 이상의 대체 지점이 강조 표시됩니다. 마우스 포인터를 대체 지점 위에 놓으면 코드 변경 방법을 설명하는 도구 설명이 나타납니다.  
  
기본적으로 Transact\-SQL 편집기에는 모든 텍스트가 표시되지만 일부 코드를 뷰에서 숨길 수도 있습니다. Transact\-SQL 편집기에서는 일부 코드 영역을 선택하여 축소 가능하게 만들 수 있습니다. 그러면 해당 영역은 더하기 기호(+) 아래에 나타나므로 코드 기호 옆에 있는 더하기 기호(+)를 클릭하여 영역을 확장하거나 숨길 수 있습니다. 개요 보기로 표시된 코드는 삭제되는 것이 아니라 단지 뷰에서 숨겨지는 것입니다.  
  
> [!WARNING]  
> 다음 절차에서는 [연결된 데이터베이스 개발](../ssdt/connected-database-development.md) 및 [프로젝트 기반 오프라인 데이터베이스 개발](../ssdt/project-oriented-offline-database-development.md) 섹션의 이전 절차에서 만들어진 엔터티를 활용합니다.  
  
### <a name="to-insert-snippets"></a>코드 조각을 삽입하려면  
  
1.  **솔루션 탐색기**에서 **TradeDev** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 후 **스크립트**를 선택합니다. **새 항목 추가** 대화 상자에서 **추가**를 클릭합니다.  
  
2.  Transact\-SQL 편집기를 마우스 오른쪽 단추로 클릭하고 **코드 조각 삽입**을 선택합니다. 코드 조각 선택기가 나타납니다.  
  
3.  코드 조각 선택기에서 **테이블**을 두 번 클릭하고 **테이블 만들기**를 두 번 클릭합니다.  
  
4.  대체 지점이 노란색으로 강조 표시됩니다. 마우스를 `Sample_Table` 위에 놓으면 정보 팁에 대체에 대한 설명이 표시됩니다. `Sample_Table`을 두 번 클릭하고 `Shipper2`로 변경합니다.  
  
5.  Tab 키를 사용하여 다음 대체 지점인 `column_1`로 이동합니다. 이름을 `Id`로 바꿉니다. 동일한 단계에 따라 `column_2`의 이름을 `name`으로 바꾸고 해당 데이터 형식을 `nvarchar(128)`로 변경한 다음 `NULL`을 허용하도록 설정합니다.  
  
### <a name="to-outline-code"></a>코드를 개요 보기로 표시하려면  
  
1.  CREATE TABLE 문 옆의 **–** 기호가 있는지 확인합니다. 스크립트의 섹션 옆에 있는 **-** 기호를 클릭하여 해당 섹션을 숨깁니다.  
  
2.  Transact\-SQL 편집기를 마우스 오른쪽 단추로 클릭하고 **개요**를 선택한 후 **개요 표시 중지**를 선택하여 편집기의 내부 코드에 영향을 주지 않고 개요 정보를 제거합니다.  
  
3.  코드의 개요 표시를 다시 시작하려면 Transact\-SQL 편집기를 마우스 오른쪽 단추로 클릭하고 **개요**를 선택한 후 **자동 개요 시작**을 선택합니다. **전체 개요 표시/숨기기**를 선택하여 섹션 확장/숨기기를 전환할 수도 있습니다.  
  