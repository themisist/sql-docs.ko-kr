---
title: 사용자 지정 보고서 항목 아키텍처 | Microsoft Docs
description: 사용자 지정 보고서 항목 아키텍처는 개발자가 RDL에서 기본적으로 지원되지 않는 기능을 추가할 수 있도록 지원되는 확장이라는 사실을 알아봅니다.
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: custom-report-items
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 039afae1b8be540869930055e77320c27857e23d
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "80216962"
---
# <a name="custom-report-item-architecture"></a>사용자 지정 보고서 항목 아키텍처
  사용자 지정 보고서 항목은 RDL(Report Definition Language)의 확장으로서 개발자는 이를 통해 RDL에서 기본적으로 지원되지 않는 기능을 추가하거나 기존 컨트롤의 기능을 확장할 수 있습니다. 사용자 지정 보고서 항목에는 런타임 구성 요소와 디자인 타임 구성 요소의 두 가지 기본 구성 요소가 있습니다. 이러한 구성 요소는 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 어셈블리로 구현되고 CLS 호환 언어로 작성할 수 있습니다.  
  
## <a name="the-run-time-component"></a>런타임 구성 요소  
 사용자 지정 보고서 항목에 대한 런타임 구성 요소는 런타임에 보고서 처리기에서 호출됩니다. 런타임 구성 요소는 런타임에 보고서 처리기에서 전달된 데이터를 수신하고 이 데이터를 처리하며 렌더링된 사용자 지정 보고서 항목이 포함된 이미지를 반환합니다.  
  
 ![사용자 지정 보고서 항목 런타임 구성 요소](../../reporting-services/custom-report-items/media/customreportitemrun-timecomponentarchitecture.gif "사용자 지정 보고서 항목 런타임 구성 요소")  
  
## <a name="the-design-time-component"></a>디자인 타임 구성 요소  
 디자인 타임 구성 요소를 활용하여 사용자 지정 보고서 항목을 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]의 보고서 디자이너 인터페이스에서 정의하고 조작할 수 있습니다. 디자인 타임 구성 요소는 디자인 환경에서 사용자 지정 보고서 항목의 모양과 속성을 제어하는 다수의 하위 컨트롤로 구성됩니다.  
  
 ![사용자 지정 보고서 항목 디자인 타임 구성 요소](../../reporting-services/custom-report-items/media/customreportitemdesign-timecomponentarchitecture.gif "사용자 지정 보고서 항목 디자인 타임 구성 요소")  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 보고서 항목 런타임 구성 요소 만들기](../../reporting-services/custom-report-items/creating-a-custom-report-item-run-time-component.md)   
 [사용자 지정 보고서 항목 디자인 타임 구성 요소 만들기](../../reporting-services/custom-report-items/creating-a-custom-report-item-design-time-component.md)   
 [방법: 사용자 지정 보고서 항목 배포](../../reporting-services/custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
