---
title: Azure Data Lake Analytics 태스크 | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2018
ms.prod: sql
ms.prod_service: integration-services
ms.component: control-flow
ms.reviewer: douglasl
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- SQL13.DTS.DESIGNER.AFPADLSTASK.F1
- SQL14.DTS.DESIGNER.AFPADLSTASK.F1
author: yanancai
ms.author: yanacai
manager: craigg
ms.openlocfilehash: 395d790069294aed541f9756fa7caefbb62f9a7b
ms.sourcegitcommit: 44e9bf62f2c75449c17753ed66bf85c43928dbd5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37854434"
---
# <a name="azure-data-lake-analytics-task"></a>Azure Data Lake Analytics 태스크

Azure Data Lake Analytics 태스크를 사용하면 사용자가 U-SQL 작업을 Azure Data Lake Analytics 서비스에 제출할 수 있습니다. [ADLA(Azure Data Lake Analytics)](https://azure.microsoft.com/services/data-lake-analytics/).

Azure Data Lake Analytics 태스크는 [Azure용 SSIS(SQL Server Integration Services) 기능 팩](../../integration-services/azure-feature-pack-for-integration-services-ssis.md)의 구성 요소입니다.

## <a name="configure-the-azure-data-lake-analytics-task"></a>Azure Data Lake Analytics 태스크 구성

패키지에 Azure Data Lake Analytics 태스크를 추가하려면 SSIS 도구 상자에서 디자이너 캔버스로 끕니다. 그런 후 태스크를 두 번 클릭하거나 태스크를 마우스 오른쪽 단추로 클릭하고 **편집**을 선택하여 **Azure Data Lake Analytics 태스크 편집기** 대화 상자를 엽니다. SSIS 디자이너를 사용하거나 프로그래밍 방식으로 속성을 설정할 수 있습니다.

## <a name="general-page-configuration"></a>일반 페이지 구성

**일반** 페이지를 사용하여 Azure Data Lake Analytics 태스크를 구성하고 태스크가 제출하는 U-SQL 스크립트를 제공합니다. U-SQL 언어에 대한 자세한 내용은 [U-SQL Language Reference](https://msdn.microsoft.com/azure/data-lake-analytics/u-sql/u-sql-language-reference)(U-SQL 언어 참조)를 참조하세요.

### <a name="basic-configuration"></a>기본 구성

- **이름**: Azure Data Lake Analytics 태스크의 이름을 지정합니다.
- **설명**: Azure Data Lake Analytics 태스크에 대한 설명을 지정합니다.

### <a name="u-sql-configuration"></a>U-SQL 구성

U-SQL 구성에는 두 개의 설정인 **SourceType** 및 **SourceType** 값을 기반으로 하는 동적 옵션이 있습니다. 

- **SourceType:** U-SQL 스크립트의 원본을 지정합니다. SSIS 패키지 실행 중에 Azure Data Lake Analytics 계정에 스크립트가 제출됩니다. 이 속성의 세 가지 옵션은 다음 표에 나열되어 있습니다.

|값|설명|  
|-----------|-----------------|  
|**DirectInput**|인라인 편집기를 통해 U-SQL 스크립트를 지정합니다. 이 값을 선택하면 동적 옵션 **USQLStatement**가 표시됩니다.|  
|**FileConnection**|U-SQL 스크립트를 포함하는 로컬 .usql 파일을 지정합니다. 이 옵션을 설정하면 동적 옵션 **FileConnection**이 표시됩니다.|  
|**변수**|U-SQL 스크립트를 포함하는 SSIS 변수를 지정합니다. 이 값을 선택하면 동적 옵션 **SourceVariable**이 표시됩니다.|

- **SourceType 동적 옵션:** U-SQL 쿼리의 스크립트 콘텐츠를 지정합니다. 

|SourceType|동적 옵션|  
|-----------|-----------------|  
|**SourceType = DirectInput**|옵션 상자에서 직접 제출할 U-SQL 쿼리를 입력하거나 [찾아보기] 단추(...)를 클릭하여 **U-SQL 쿼리 입력** 대화 상자에 U-SQL 쿼리를 입력합니다.|  
|**SourceType = FileConnection**|기존 파일 연결 관리자를 선택하거나 <**새 연결...**>을 클릭하여 새 연결 관리자를 만듭니다. **관련 문서:** [파일 연결 관리자](../../integration-services/connection-manager/file-connection-manager.md), [파일 연결 관리자 편집기](../../integration-services/connection-manager/file-connection-manager-editor.md)|  
|**SourceType = Variable**|기존 변수를 선택하거나 \<**새 변수...**>를 클릭하여 새 변수를 만듭니다. **관련 문서**: [Integration Services&#40;SSIS&#41; 변수](../../integration-services/integration-services-ssis-variables.md), [변수 추가](http://msdn.microsoft.com/library/d09b5d31-433f-4f7c-8c68-9df3a97785d5)|


### <a name="job-configuration"></a>작업 구성
작업 구성은 U-SQL 작업 제출 속성을 지정합니다.

- **AzureDataLakeAnalyticsConnection:** U-SQL 스크립트가 제출될 Azure Data Lake Analytics 계정을 지정합니다. 정의된 연결 관리자 목록에서 연결을 선택합니다. 새 연결을 만들려면 <**새 연결...**>을 선택합니다. 관련 문서: [Azure Data Lake Analytics 연결 관리자](../../integration-services/connection-manager/azure-data-lake-analytics-connection-manager.md).

- **JobName:** U-SQL 작업의 이름을 지정합니다. 
- **AnalyticsUnits:** U-SQL 작업의 분석 단위 수를 지정합니다.
- **Priority:** U-SQL 작업의 우선 순위를 지정합니다. 우선 순위는 0~1000 사이에서 설정할 수 있고 숫자가 작을수록 우선 순위가 높습니다.
- **RuntimeVersion:** U-SQL 작업의 Azure Data Lake Analytics 런타임 버전을 지정합니다. 기본적으로 “default”로 설정됩니다. 일반적으로 이 속성을 변경할 필요가 없습니다.
- **Synchronous:** 작업 실행이 완료될 때까지 태스크가 기다릴지 여부를 지정하는 부울 값입니다. True로 설정하면 작업이 완료된 후 태스크가 성공으로 표시됩니다. False로 설정하면 작업이 준비 단계를 통과한 후 태스크가 성공으로 표시됩니다.

|값|설명|
|-----------|-----------------|
|True|태스크 결과는 U-SQL 작업 실행 결과를 기반으로 합니다. 작업 성공 --> 태스크 성공, 작업 실패 --> 태스크 실패, 태스크 성공 또는 실패 --> 태스크 완료.|
|False|태스크 결과는 U-SQL 작업 제출 및 준비 결과를 기반으로 합니다. 작업 제출 성공 및 준비 단계 통과 --> 태스크 성공, 작업 제출 실패 또는 준비 단계에서 작업 실패 --> 태스크 실패, 태스크 성공 또는 실패 --> 태스크 완료.|

- **TimeOut:** 작업 실행을 위한 시간 제한 시간(초)을 지정합니다. 작업 시간이 초과된 후 작업이 취소되고 태스크가 실패로 표시됩니다. Synchronous가 False로 설정되면 TimeOut 속성을 사용할 수 없습니다. **Synchronous**가 **false**로 설정되면 TimeOut 속성을 사용할 수 없습니다.

## <a name="parameter-mapping-page-configuration"></a>매개 변수 매핑 페이지 구성

**Azure Data Lake Analytics 태스크 편집기** 대화 상자의 **매개 변수 매핑** 페이지를 사용하여 변수를 U-SQL 스크립트의 매개 변수(U-SQL 변수)에 매핑합니다.

- **변수 이름:** **추가**를 클릭하여 매개 변수 매핑을 추가했으면 **변수 추가** 대화 상자를 사용하여 목록에서 시스템 또는 사용자 정의 변수를 선택하거나 \<**새 변수...**>를 클릭하여 새 변수를 추가합니다. **관련 항목:** [Integration Services&#40;SSIS&#41; 변수](../../integration-services/integration-services-ssis-variables.md)  

- **매개 변수 이름:** U-SQL 스크립트에 매개 변수/변수 이름을 제공합니다. 매개 변수 이름이 @Param1과 같이 @ 기호로 시작하는지 확인합니다. 

다음은 U-SQL 스크립트에 매개 변수를 전달하는 방법의 예제입니다.

**샘플 U-SQL 스크립트**
```
@searchlog =
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int,
            Urls            string,
            ClickedUrls     string
    FROM @in
    USING Extractors.Tsv(nullEscape:"#NULL#");

@rs1 =
    SELECT Start, Region, Duration
    FROM @searchlog
WHERE Region == "en-gb";

@rs1 =
    SELECT Start, Region, Duration
    FROM @rs1
    WHERE Start <= DateTime.Parse("2012/02/19");

OUTPUT @rs1   
    TO @out
      USING Outputters.Tsv(quoting:false, dateTimeFormat:null);
```

위의 스크립트 예제에서 입력 및 출력 경로는 **@in** 및 **@out** 매개 변수에 정의됩니다. U-SQL 스크립트에서 **@in** 및 **@out** 매개 변수의 값은 매개 변수 매핑 구성을 통해 동적으로 전달됩니다.

|변수 이름|매개 변수 이름|
|-------------|--------------|
|사용자: Variable1|@in|
|사용자: Variable2|@out| 

## <a name="expression-page-configuration"></a>식 페이지 구성

일반 페이지 구성의 모든 속성을 속성 식으로 할당하면 런타임에 속성의 동적 업데이트를 사용할 수 있습니다. **관련 항목**: [패키지에서 속성 식 사용](../../integration-services/expressions/use-property-expressions-in-packages.md)

## <a name="see-also"></a>참고 항목
- [Azure Data Lake Analytics 연결 관리자](../../integration-services/connection-manager/azure-data-lake-analytics-connection-manager.md)
- [Azure Data Lake Store 파일 시스템 태스크](../../integration-services/control-flow/azure-data-lake-store-file-system-task.md)
- [Azure Data Lake Store 연결 관리자](../../integration-services/connection-manager/azure-data-lake-store-connection-manager.md)
