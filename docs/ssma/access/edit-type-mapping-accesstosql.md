---
title: 형식 매핑 편집 (AccessToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 7f9d9530-6c04-41d9-bbe7-d91820a30066
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 7d41fc2f01e2cfbc2b20c58ea9be640f2afd8ea0
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68006576"
---
# <a name="edit-type-mapping-accesstosql"></a>형식 매핑 편집 (AccessToSQL)
**유형 매핑 편집** 대화 상자를 사용 하 여 원본 및 대상 데이터베이스 개체 간에 유형을 매핑하는 방법을 지정할 수 있습니다.  
  
이 대화 상자는 여러 위치에서 액세스할 수 있습니다.  
  
-   원본 데이터베이스 또는 데이터베이스 개체를 선택 하면 메타 데이터 탐색기의 오른쪽에 **형식 매핑** 탭이 나타납니다. 새 형식 매핑을 추가 하려면 **추가** 를 클릭 하 고, 기존 형식 매핑을 변경 하려면 **편집** 을 클릭 합니다.  
  
-   **도구** 메뉴에서 **프로젝트 설정** 또는 **기본 프로젝트 설정**을 선택 합니다. 결과 대화 상자에서 **형식 매핑**을 선택 합니다. 새 형식 매핑을 추가 하려면 **추가** 를 클릭 하 고, 기존 형식 매핑을 변경 하려면 **편집** 을 클릭 합니다.  
  
테이블 관련 형식 매핑은 데이터베이스 및 프로젝트 형식 매핑을 재정의 합니다. 데이터베이스 관련 매핑은 프로젝트 매핑을 재정의 합니다.  
  
## <a name="options"></a>옵션  
**원본 유형**  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식에 매핑할 원본 데이터 형식을 선택 합니다.  
  
데이터 형식이 가변 길이인 경우 **원본 유형**아래에 다음 필드가 표시 됩니다.  
  
**From**  
이 매핑의 최소 길이를 지정 합니다. 예를 들어 **텍스트** 데이터 형식의 경우 10을 입력 하 여이 매핑이 **텍스트 (10)** 에서 시작 하는 범위에 대 한 매핑 임을 지정할 수 있습니다.  
  
**받는 사람**  
이 매핑의 최대 길이를 지정 합니다. 예를 들어 **텍스트** 데이터 형식의 경우 20을 입력 하 여이 매핑이 **텍스트 (20)** 로 끝나는 범위에 대해 지정 되도록 지정할 수 있습니다.  
  
**대상 형식**  
원본 데이터 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 형식이 매핑되는 데이터 형식을 선택 합니다. SSMA에서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]테이블이 나 저장 프로시저를 만들 때 원본 데이터 형식이이 데이터 형식으로 변경 됩니다.  
  
데이터 형식이 가변 길이인 경우 **대상 유형**아래에 다음 필드가 표시 됩니다.  
  
**바꿀 내용**  
이 매핑의 대상 길이를 지정 합니다. 예를 들어 **nvarchar** 데이터 형식의 경우 20을 입력 하 여 지정 된 원본 데이터 형식을 **nvarchar (20)** 로 매핑해야 함을 지정할 수 있습니다.  
  
