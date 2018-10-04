---
title: Azure Data Studio에서 소스 제어 | Microsoft Docs
description: Azure Data Studio에서 소스 제어를 구성 하는 방법에 알아봅니다.
ms.custom: tools|sos
ms.date: 09/24/2018
ms.prod: sql
ms.reviewer: alayu; sstein
ms.prod_service: sql-tools
ms.topic: conceptual
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 2dd424922c4f21c8822a74c49b56723467ac6fed
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "48039193"
---
#  <a name="using-source-control-in-includename-sosincludesname-sos-shortmd"></a>소스 제어를 사용 하 여 [!INCLUDE[name-sos](../includes/name-sos-short.md)]

[!INCLUDE[name-sos](../includes/name-sos-short.md)] 버전/소스 제어에 Git를 지원합니다.


## <a name="git-support-in-includename-sosincludesname-sos-shortmd"></a>Git 지원 [!INCLUDE[name-sos](../includes/name-sos-short.md)]

[!INCLUDE[name-sos](../includes/name-sos-short.md)] Git 소스 제어 관리자 (SCM) 같지만 제공 해야 [Git 설치 (버전 2.0.0 이상)](https://git-scm.com/download) 전에 이러한 기능을 사용할 수 있습니다. 



## <a name="open-an-existing-git-repository"></a>기존 Git 리포지토리를 열려면

1. 아래는 **파일** 메뉴에서 **폴더 열기...**
2. Git에서 추적 파일이 포함 된 폴더로 이동 하 고 클릭 **폴더 선택**합니다. 로컬 리포지토리의 하위 폴더 여기에서 선택 해도 됩니다.


## <a name="initialize-a-new-git-repository"></a>새 git 리포지토리를 초기화 합니다.

1. 선택 **소스 제어**, git 아이콘을 선택 합니다.

   ![소스 제어 git 아이콘](media/source-control/source-control.png)

1. Git 리포지토리를 눌러로 초기화 하려는 폴더의 경로를 입력 **Enter**합니다.

   ![Git 리포지토리를 초기화 합니다.](media/source-control/initialize-git-repository.png)

## <a name="working-with-git-repositories"></a>Git 리포지토리 사용

[!INCLUDE[name-sos](../includes/name-sos-short.md)] VS Code에서 Git 구현을 상속 되지만 추가 SCM 공급자를 현재 지원 하지 않습니다. 열거나 리포지토리를 초기화 한 후 Git를 사용 하는 방법에 대 한 세부 정보를 참조 하세요 [VS Code의 Git 지원을](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support)합니다.


## <a name="additional-resources"></a>추가 리소스
- [Git 설명서](https://git-scm.com/documentation)