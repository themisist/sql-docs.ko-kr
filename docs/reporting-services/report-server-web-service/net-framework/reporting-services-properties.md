---
title: Reporting Services 속성 | Microsoft Docs
description: 보고서 서버는 전역 시스템 속성과 개별 항목 속성을 정의합니다. 애플리케이션은 시스템 및 항목 속성에 사용자 정의 속성을 추가할 수 있습니다.
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-web-service
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7240bf3e987c5817489035d94879817f5f39569b
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "79509714"
---
# <a name="reporting-services-properties"></a>Reporting Services 속성
  보고서 서버에서는 보고서 서버의 전역 시스템 속성 집합 및 보고서 서버 데이터베이스에 저장된 개별 항목과 연결된 항목 속성 집합을 정의합니다. 보고서 서버에서 정의된 속성은 삭제할 수 없으며 읽기 전용인 경우도 있습니다. 애플리케이션에서 추가 사용자 정의 속성을 시스템 및 항목 속성에 추가하여 시스템 속성 및 항목 속성을 확장할 수 있습니다.  
  
 다음 웹 서비스 메서드는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 속성을 검색하고 설정합니다.  
  
|방법|작업|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|보고서 서버 데이터베이스의 항목에 대한 속성 값을 하나 이상 반환합니다.|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|시스템 속성을 하나 이상 반환합니다.|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|보고서 서버 데이터베이스의 항목에 대한 속성을 하나 이상 설정합니다.|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|시스템 속성을 하나 이상 설정합니다.|  
  
## <a name="in-this-section"></a>섹션 내용  
  
|항목|Description|  
|-----------|-----------------|  
|[보고서 서버 항목 속성](../../../reporting-services/report-server-web-service/net-framework/reporting-services-properties-report-server-item-properties.md)|[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]의 항목별 속성에 대해 설명합니다.|  
|[보고서 서버 시스템 속성](../../../reporting-services/report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md)|[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]의 시스템별 속성에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [웹 서비스와 .NET Framework를 사용하여 애플리케이션 빌드](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [보고서 서버 웹 서비스](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [기술 참조&#40;SSRS&#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  
