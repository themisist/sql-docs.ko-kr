---
title: 버전에 플래그 할당
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 90ffe973c15df9d17eb1080f0e6b681791485681
ms.sourcegitcommit: 6be9a0ff0717f412ece7f8ede07ef01f66ea2061
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85814034"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a>버전에 플래그 할당(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 사용자나 구독 시스템에서 사용해야 하는 버전을 지정하려면 버전에 플래그를 할당합니다.  
  
> [!NOTE]  
>  버전 플래그는 한 번에 한 버전에만 할당할 수 있습니다. 다른 버전에 이미 할당되어 있는 플래그를 할당하는 경우에는 플래그가 선택한 버전으로 이동됩니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 절차를 수행하려면  
  
-   **버전 관리** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다.  
  
-   모델 관리자여야 합니다. 자세한 내용은 [관리자 &#40;MDS(Master Data Services)&#41;](../master-data-services/administrators-master-data-services.md)를 참조 하세요.  
  
-   할당하려는 버전 플래그를 미리 만들어 두어야 합니다. 자세한 내용은 [버전 플래그 만들기&#40;Master Data Services&#41;](../master-data-services/create-a-version-flag-master-data-services.md)를 참조하세요.  
  
-   버전 관리 기능 영역에 액세스할 수 있는 권한이 있어야 합니다. 자세한 내용은 [기능 영역 권한&#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md)을 참조하세요.  
  
### <a name="to-assign-a-flag-to-a-version"></a>버전에 플래그를 할당하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 **버전 관리**를 클릭합니다.  
  
2.  **버전 관리** 페이지에서 플래그를 할당하려는 버전 행의 **플래그** 열에 있는 셀을 두 번 클릭합니다.  
  
3.  목록에서 할당할 플래그를 선택합니다.  
  
    > [!NOTE]  
    >  원하는 플래그를 사용할 수 없는 경우 **커밋됨** 버전에만 플래그를 사용할 수 있기 때문일 수 있습니다. 확인하려면 **버전 플래그 관리** 페이지로 이동하여 플래그의 **커밋된 버전만** 필드를 봅니다.  
  
4.  Enter 키를 눌러 변경 내용을 저장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDS(Master Data Services) &#40;버전 플래그를 만듭니다&#41;](../master-data-services/create-a-version-flag-master-data-services.md)   
 [버전&#40;Master Data Services&#41;](../master-data-services/versions-master-data-services.md)  
  
  
