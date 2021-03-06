---
title: 공유 데이터 세트 캐시 | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7e98e5ffd8970806e2ed92e53c8e82da21387938
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "65574764"
---
# <a name="cache-a-shared-dataset"></a>공유 데이터 세트 캐시
  성능을 향상시키는 한 가지 방법은 공유 데이터 세트의 캐싱 속성을 구성하는 것입니다. 공유 데이터 세트가 캐시되면 쿼리 결과의 복사본이 지정된 기간 동안 저장됩니다. 공유 데이터 세트를 사용하는 보고서를 요청하는 첫 번째 사용자는 쿼리 결과 및 모든 처리가 완료될 때까지 기다려야 보고서를 볼 수 있습니다. 캐싱 기간 내에 보고서를 요청하는 이후 사용자는 쿼리 및 처리가 이미 발생했기 때문에 기다리지 않고 볼 수 있습니다. 또한 쿼리를 실행하고 지정된 캐시 만료 시점까지 결과를 캐시하기 위한 캐시 새로 고침 계획을 지정할 수도 있습니다.  
  
 공유 데이터 세트 또는 캐시 새로 고침 계획을 기반으로 보고서를 실행하는 사용자는 쿼리 캐시를 만들며 두 경우 모두 캐시 만료 옵션에 따라 캐시를 사용할 수 있습니다.  
  
 캐시할 수 있는 공유 데이터 세트 유형은 제한되어 있습니다. 예를 들어 사용자 ID에 따라 데이터가 달라지는 경우 또는 보고서를 요청하는 사용자의 보안 토큰을 사용하여 데이터가 검색되는 경우 쿼리 결과를 캐시할 수 없습니다. 자세한 내용은 [공유 데이터 세트 캐시&#40;SSRS&#41;](../../reporting-services/report-server/cache-shared-datasets-ssrs.md) 및 [보고서 캐시&#40;SSRS&#41;](../../reporting-services/report-server/caching-reports-ssrs.md)을 참조하세요.  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a>캐시된 보고서의 만료를 예약하려면  
  
1.  [보고서 관리자&#40;SSRS 기본 모드&#41;](https://msdn.microsoft.com/library/80949f9d-58f5-48e3-9342-9e9bf4e57896)를 시작합니다.  
  
2.  보고서 관리자에서 캐싱 속성을 설정할 공유 데이터 세트로 이동하여 항목 위로 마우스를 이동하고 드롭다운 화살표를 클릭합니다.  
  
3.  드롭다운 메뉴에서 **관리**를 클릭합니다.  
  
4.  왼쪽 프레임에서 **캐싱**을 클릭합니다.  
  
    > [!NOTE]  
    >  **공유 데이터 세트를 실행하는 데 사용되는 자격 증명이 저장되어 있지 않습니다**라는 오류가 표시되면 공유 데이터 세트 캐시 옵션이 비활성화됩니다. 데이터 원본을 수정하여 자격 증명을 저장하거나 공유 데이터 세트를 수정하여 자격 증명이 저장되어 있는 다른 데이터 원본을 사용해야 합니다.  
  
5.  **공유 데이터 세트 캐시**를 선택합니다.  
  
6.  30분 후에 캐시가 만료되는 옵션을 선택합니다. 지정된 일정에 따라 캐시가 만료되는 옵션을 선택할 수도 있습니다.  
  
7.  **적용**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유 데이터 세트 관리](../../reporting-services/report-data/manage-shared-datasets.md)  
  
  
