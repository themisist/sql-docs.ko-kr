---
title: TuningOptions 요소(DTA)
description: dta 유틸리티에서 TuningOptions 요소는 특정 튜닝 세션에 대한 튜닝 옵션을 포함합니다.
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.openlocfilehash: e23ba0eef792e64a9f2b8d6e6f95ec1b793b71fc
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85774970"
---
# <a name="tuningoptions-element-dta"></a>TuningOptions 요소(DTA)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

특정 튜닝 세션에 대한 튜닝 옵션을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특성|Description|  
|--------------------|-----------------|  
|**데이터 형식 및 길이**|없음|  
|**기본값**|없음|  
|**발생 빈도**|(선택 사항) 사용할 경우 각 **DTAInput** 요소에 한 번만 사용할 수 있습니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|--------------|  
|**부모 요소**|[DTAInput 요소&#40;DTA&#41;](../../tools/dta/dtainput-element-dta.md)|  
|**자식 요소**|**ReportSet** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> **TuningLogTable** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> **NumberOfEvents** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> [TuningTimeInMin 요소&#40;DTA&#41;](../../tools/dta/tuningtimeinmin-element-dta.md)<br /><br /> [StorageBoundInMB 요소&#40;DTA&#41;](../../tools/dta/storageboundinmb-element-dta.md)<br /><br /> **MaxKeyColumnsInIndex** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> **MaxColumnsInIndex** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> **MinPercentageImprovement** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> [TestServer 요소&#40;DTA&#41;](../../tools/dta/testserver-element-dta.md)<br /><br /> [FeatureSet 요소&#40;DTA&#41;](../../tools/dta/featureset-element-dta.md)<br /><br /> [Partitioning 요소&#40;DTA&#41;](../../tools/dta/partitioning-element-dta.md)<br /><br /> [DropOnlyMode 요소&#40;DTA&#41;](../../tools/dta/droponlymode-element-dta.md)<br /><br /> [KeepExisting 요소&#40;DTA&#41;](../../tools/dta/keepexisting-element-dta.md)<br /><br /> [OnlineIndexOperation 요소&#40;DTA&#41;](../../tools/dta/onlineindexoperation-element-dta.md)<br /><br /> [DatabaseToConnect 요소&#40;DTA&#41;](../../tools/dta/databasetoconnect-element-dta.md)<br /><br /> **IgnoreConstantsInWorkload** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.<br /><br /> **RetainShellDB** 요소입니다. 자세한 내용은 [데이터베이스 엔진 튜닝 관리자 XML 스키마](https://go.microsoft.com/fwlink/?linkid=43100)를 참조하십시오.|  
  
## <a name="example"></a>예제  
 **TuningOptions** 요소의 예제는 [XML 입력 파일 샘플&#40;DTA&#41;](../../tools/dta/xml-input-file-samples-dta.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 입력 파일 참조&#40;데이터베이스 엔진 튜닝 관리자&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
