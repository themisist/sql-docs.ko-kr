---
title: SQL Server 구성 요소에 연결
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: markingmyname
ms.author: maghan
ms.openlocfilehash: ebc0f4a5ca2be46e607ccd8d18399b7fe0ef6814
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "75243934"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a>SQL Server Management Studio에서 SQL Server 구성 요소로 연결
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 모든 구성 요소를 관리하기 위한 기능을 제공합니다. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 를 사용하여 다음과 연결할 수 있습니다.  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]인스턴스  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion_md.md)]입니다.  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]입니다.  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]입니다.  
  
[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 에서는 데이터 원본에 먼저 연결하지 않은 상태에서 쿼리 작업을 할 수 있지만 대부분의 다른 태스크를 하려면 연결이 필요합니다. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**구성 요소에 대한 연결 속성을 구성하기 위한** 서버에 연결 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대화 상자를 제공합니다. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 가 시작되면 **서버에 연결** 대화 상자가 열리고 서버에 연결하라는 메시지가 나타납니다. **서버에 연결** 대화 상자에서는 마지막으로 사용된 연결 설정이 유지됩니다.  
  
> [!NOTE]  
> 연결이 자동으로 시작되지 않도록 이 기능을 해제할 수 있습니다. 자세한 내용은 [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md)을(를) 참조하세요.  
  
## <a name="saving-connections"></a>연결 저장  
특정 서버에 대한 연결을 등록된 서버에 저장하거나 솔루션 탐색기를 사용하여 연결을 프로젝트에 저장할 수 있습니다.  
  
### <a name="saving-connections-in-registered-servers"></a>등록된 서버에 연결 저장  
서버를 등록하면 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 는 연결 정보를 등록된 서버에 저장합니다. 등록된 서버에 연결하려면 등록된 서버에서 서버 이름을 두 번 클릭합니다. 그러면 개체 탐색기에서 서버에 대한 연결이 열립니다.  
  
### <a name="saving-connections-in-solution-explorer"></a>솔루션 탐색기에서 연결 저장  
솔루션 탐색기를 사용하면 관련 쿼리, 스크립트, 연결 및 기타 관련 정보를 프로젝트에 저장할 수 있습니다. 각 스크립트 프로젝트에는 하나 이상의 연결을 저장할 수 있는 **연결**이라는 노드가 포함되어 있습니다. 연결을 추가하려면 **연결**을 마우스 오른쪽 단추로 클릭한 다음 **새 연결**을 클릭합니다. 저장된 연결에 액세스하려면 **연결** 을 확장하고 연결을 두 번 클릭합니다. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 해당 연결과 연관된 쿼리 창이 열립니다. 저장 시 스크립트에서는 특정 연결과의 연관성이 유지됩니다.  
  
## <a name="see-also"></a>참고 항목  
[SQL Server Management Studio 사용](../../ssms/use-sql-server-management-studio.md)  
[개체 탐색기](../../ssms/object/object-explorer.md)  
  
