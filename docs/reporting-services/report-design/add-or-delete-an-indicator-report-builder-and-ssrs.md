---
title: 표시기 추가 또는 삭제(보고서 작성기) | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 08dd396fc68bae04d973d6b96f67466006642120
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "77081566"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a>표시기 추가 또는 삭제(보고서 작성기 및 SSRS)
  [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] 페이지를 매긴 보고서에서 표시기는 단일 데이터 값의 상태를 한눈에 볼 수 있는 최소 계기입니다. 자세한 내용은 [표시기&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/indicators-report-builder-and-ssrs.md)를 참조하세요.  
  
 표시기는 일반적으로 테이블이나 행렬의 셀에 배치되지만 계기와 함께 또는 계기에 포함하여 표시기를 독립적으로 사용할 수도 있습니다.  
  
 표시기를 처음 추가하면 기본적으로 백분율을 단위로 사용하도록 표시기가 구성됩니다. 백분율 범위는 표시기 집합의 멤버 간에 균등하게 분포되며 표시기가 나타내는 값의 범위는 테이블이나 행렬과 같은 표시기의 부모입니다.  
  
 표시기의 값과 상태를 업데이트할 수 있습니다. 자세한 내용은 아래 항목을 참조하세요.  
  
-   [표시기 아이콘 및 표시기 집합 변경&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [단위 설정 및 구성&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [동기화 범위 설정&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/set-synchronization-scope-report-builder-and-ssrs.md)  
  
 표시기가 계기 패널 내부에 배치되기 때문에 **표시기 속성** 대화 상자나 **속성** 창을 사용하여 표시기를 구성할 때 패널 대신 표시기를 선택해야 합니다. 다음 그림에서는 계기 패널에서 선택된 표시기를 보여 줍니다.  
  
 ![rs_GaugePanelWithIndicator](../../reporting-services/report-design/media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")  
  
> [!NOTE]  
>  열 너비와 데이터 값의 길이에 따라 테이블 또는 행렬 셀의 텍스트가 자동으로 줄이 바뀌고 여러 줄로 표시될 수 있습니다. 이 경우 표시기 아이콘이 늘어나고 모양이 바뀔 수 있습니다. 그러면 표시기 아이콘의 가독성이 떨어질 수 있습니다. 표시기를 사각형 안에 배치하여 아이콘이 늘어나지 않도록 하십시오.  
  
## <a name="to-add-an-indicator-to-a-table-or-matrix"></a>테이블 또는 행렬에 표시기를 추가하려면  
  
1.  기존 보고서를 열거나 표시할 데이터가 있는 테이블 및 행렬을 포함하는 새 보고서를 만듭니다. 자세한 내용은 [테이블&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/tables-report-builder-and-ssrs.md) 또는 [행렬](../../reporting-services/report-design/create-a-matrix-report-builder-and-ssrs.md)을 참조하세요.  
  
2.  테이블이나 행렬에 열을 삽입합니다. 자세한 내용은 [열 삽입 또는 삭제&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/insert-or-delete-a-column-report-builder-and-ssrs.md)를 참조하세요.  
  
3.  필요한 경우 **삽입** 탭에서 **사각형**을 클릭한 다음 새 열의 셀을 클릭합니다.  
  
4.  **삽입** 탭에서 **표시기**를 클릭한 다음 새 열의 셀을 클릭합니다.  
  
     셀에 사각형을 추가한 경우 해당 셀을 클릭합니다.  
  
5.  **표시기 스타일 선택** 대화 상자의 왼쪽 창에서 원하는 표시기 유형을 클릭한 다음 표시기 집합을 클릭합니다.  
  
6.  **확인**을 클릭합니다.  
  
7.  표시기를 클릭합니다. **계기 데이터** 창이 열립니다.  
  
8.  **값** 영역의 **(지정되지 않음)** 드롭다운 목록에서 값을 표시기로 표시할 필드를 클릭합니다.  
  
     표시기는 기본값을 사용하도록 구성됩니다. 기본적으로 표시기는 백분율을 단위로 사용하도록 구성되며 백분율 범위는 표시기의 멤버 간에 균등하게 분포되고 표시기가 제공하는 값은 가장 가까운 그룹의 범위를 사용합니다.  
  
## <a name="to-delete-an-indicator-to-a-table-or-matrix"></a>테이블 또는 행렬에서 표시기를 삭제하려면  
  
1.  삭제할 표시기를 마우스 오른쪽 단추로 클릭하고 **삭제**를 클릭합니다.  
  
    > [!NOTE]  
    >  표시기는 다른 표시기나 계기가 포함된 계기 패널 안에 배치될 수 있습니다. 계기 패널에 여러 항목이 포함된 경우 표시기를 삭제하려면 계기 패널이 아니라 표시기를 클릭해야 합니다. 계기 패널을 클릭한 다음 삭제하면 계기 패널과 그 안의 모든 항목이 삭제됩니다.  
  
2.  **삭제**를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [표시기&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/indicators-report-builder-and-ssrs.md)  
  
  
