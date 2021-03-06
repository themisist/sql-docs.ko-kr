---
title: 분석 보고서 만들기
description: 데이터베이스 실험 도우미에서 분석 보고서를 생성 합니다 (DEA). 분석 보고서는 제안 된 변경 내용의 성능 영향에 대 한 정보를 제공 합니다.
ms.date: 01/24/2020
ms.prod: sql
ms.prod_service: dea
ms.suite: sql
ms.technology: dea
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: HJToland3
ms.author: jtoland
ms.reviewer: mathoma
ms.custom: seo-lt-2019
ms.openlocfilehash: 09f8ab0b3f4950e06c96b67c74f9cdcbc09269d5
ms.sourcegitcommit: b80364e31739d7b08cc388c1f83bb01de5dd45c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87565570"
---
# <a name="create-analysis-reports-in-database-experimentation-assistant-sql-server"></a>데이터베이스 실험 도우미에서 분석 보고서 만들기 (SQL Server)

두 대상 서버 모두에서 원본 추적을 재생 한 후에는 데이터베이스 실험 도우미 (DEA)에서 분석 보고서를 생성할 수 있습니다. 분석 보고서를 통해 제안 된 변경 내용의 성능 영향에 대 한 정보를 얻을 수 있습니다.

## <a name="create-an-analysis-report"></a>분석 보고서 만들기

1. DEA에서 목록 아이콘을 선택 하 고, 서버 이름 및 인증 유형을 지정 하 고, 시나리오에 적절 하 게 **연결 암호화** 및 **서버 인증서 신뢰** 확인란을 선택 하거나 선택 취소 한 다음 **연결**을 선택 합니다.

   ![추적 파일을 사용 하 여 서버에 연결](./media/database-experimentation-assistant-create-report/dea-connect-to-server-with-trace-files.png)

2. **분석 보고서** 화면에서 **새 분석 보고서**를 선택 합니다.

   ![새 분석 보고서 만들기](./media/database-experimentation-assistant-create-report/dea-create-an-analysis-report.png)

3. **새 분석 보고서** 화면에서 보고서 이름, 저장소 위치 및 대상 1과 대상 2 추적 파일의 경로를 지정 하 고 **시작**을 선택 합니다.

   ![새 분석 보고서 정보 지정](./media/database-experimentation-assistant-create-report/dea-new-analysis-report-details.png)

   입력 한 정보가 올바르면 분석 보고서가 생성 됩니다.

   ![새로 만든 분석 보고서](./media/database-experimentation-assistant-create-report/dea-newly-created-analysis-report.png)

      > [!NOTE]
      > 입력 한 정보가 잘못 된 경우 잘못 된 정보를 포함 하는 입력란은 빨간색으로 강조 표시 됩니다. 필요한 수정 작업을 수행 하 고 다시 **시작** 을 선택 합니다.

## <a name="frequently-asked-questions-about-analysis-reports"></a>분석 보고서에 대 한 질문과 대답

**Q: 분석 보고서는 어떻게 설명 하나요?**

DEA는 통계 테스트를 사용 하 여 워크 로드를 분석 하 고 각 쿼리가 대상 1에서 대상 2로 실행 되는 방법을 결정 합니다. 각 쿼리에 대 한 성능 정보를 제공 합니다. [시작 하기](database-experimentation-assistant-get-started.md)에서 DEA에 대해 자세히 알아보세요.

**Q: 다른 보고서를 생성 하는 동안 새 분석 보고서를 만들 수 있나요?**

아니요.  현재는 충돌을 방지 하기 위해 한 번에 하나의 보고서만 생성할 수 있습니다. 그러나 둘 이상의 캡처 및 재생을 동시에 실행할 수 있습니다.

**Q: 명령 프롬프트를 사용 하 여 분석 보고서를 생성할 수 있습니까?**

예. 명령 프롬프트에서 분석 보고서를 생성할 수 있습니다. 그런 다음 UI에서 보고서를 볼 수 있습니다. 자세한 내용은 [명령 프롬프트에서 실행](database-experimentation-assistant-run-command-prompt.md)을 참조 하세요.

## <a name="troubleshoot-analysis-reports"></a>분석 보고서 문제 해결

**Q: 내 서버에서 분석 보고서를 생성 하 고 확인 하는 데 필요한 보안 권한은 무엇입니까?**

DEA에 로그인 한 사용자에 게는 analysis server에 대 한 sysadmin 권한이 있어야 합니다. 사용자가 그룹의 일부인 경우 그룹에 sysadmin 권한이 있는지 확인 합니다.

|가능한 오류|해결 방법|  
|---|---|  
|데이터베이스에 연결할 수 없습니다. 보고서를 분석 하 고 볼 수 있는 sysadmin 권한이 있는지 확인 합니다.|서버 또는 데이터베이스에 대 한 액세스 또는 sysadmin 권한이 없을 수 있습니다. 로그인 권한을 확인 하 고 다시 시도 하세요.|  
|서버 **서버 이름**에 대 한 **보고서 이름을** 생성할 수 없습니다. 자세한 내용은 **보고서 이름** 보고서를 참조 하세요.|새 보고서를 생성 하는 데 필요한 sysadmin 권한이 없을 수 있습니다. 자세한 오류를 보려면 오류 발생 보고서를 선택 하 고% temp% DEA의 로그를 확인 하십시오 \\ .|  
|현재 사용자에 게 작업을 실행 하는 데 필요한 권한이 없습니다. 추적을 수행 하 고 보고서를 분석 하기 위한 sysadmin 권한이 있는지 확인 합니다.|새 보고서를 생성 하는 데 필요한 sysadmin 권한이 없습니다.|  

**Q: SQL Server를 실행 하는 컴퓨터에 연결할 수 없습니다.**

- SQL Server를 실행 하는 컴퓨터의 이름이 올바른지 확인 합니다. 확인 하려면 SSMS (SQL Server Management Studio)를 사용 하 여 서버에 연결을 시도 합니다.
- 방화벽 구성이 SQL Server를 실행 하는 컴퓨터에 대 한 연결을 차단 하지 않는지 확인 합니다.
- 사용자에 게 필요한 사용자 권한이 있는지 확인 합니다.

% Temp% DEA의 로그에서 자세한 내용을 볼 수 있습니다 \\ . 문제가 지속 되 면 제품 팀에 문의 하십시오.

**Q: 분석 보고서를 생성할 때 오류가 표시 됩니다.**

DEA를 설치한 후 처음으로 분석 보고서를 생성할 때 인터넷에 액세스할 수 있어야 합니다. 통계 분석에 필요한 패키지를 다운로드 하려면 인터넷에 액세스 해야 합니다.

보고서를 만드는 동안 오류가 발생 하는 경우 진행률 페이지에 분석을 생성 하지 못한 특정 단계가 표시 됩니다. % Temp% DEA의 로그에서 자세한 내용을 볼 수 있습니다 \\ . 필요한 사용자 권한으로 서버에 대 한 올바른 연결이 있는지 확인 한 후 다시 시도 하십시오. 문제가 지속 되 면 제품 팀에 문의 하십시오.

|가능한 오류|해결 방법|  
|---|---|  
|RInterop 시작 시 오류가 발생 했습니다. RInterop 로그를 확인 하 고 다시 시도 하세요.|DEA에서 종속 R 패키지를 다운로드 하려면 인터넷에 액세스할 수 있어야 합니다. % Temp% DEA 의% temp% \\ rinterop 및 DEA 로그에서 rinterop 로그를 확인 하십시오 \\ . RInterop가 잘못 초기화 되었거나 올바른 R 패키지 없이 초기화 된 경우 DEA 로그의 InitializeRInterop 단계 후에 "새 분석 보고서를 생성 하지 못했습니다" 라는 예외가 표시 될 수 있습니다.<br><br>RInterop 로그에 "사용할 수 있는 jsonlite 패키지가 없습니다."와 유사한 오류가 표시 될 수도 있습니다. 컴퓨터에서 인터넷에 액세스할 수 없는 경우 필요한 jsonlite R 패키지를 수동으로 다운로드할 수 있습니다.<br><br><li>\\컴퓨터의 파일 시스템 에서% userprofile% dearpackages 폴더로 이동 합니다. 이 폴더는 DEA에서 R에 사용 되는 패키지로 구성 됩니다.</li><br><li>Jsonlite 폴더가 설치 된 패키지 목록에 없는 경우에서 jsonlite1.4.zip의 릴리스 버전을 다운로드 하려면 인터넷에 액세스할 수 있는 컴퓨터가 필요 \_ [https://cran.r-project.org/web/packages/jsonlite/index.html](https://cran.r-project.org/web/packages/jsonlite/index.html) 합니다.</li><br><li>DEA를 실행 하는 컴퓨터에 .zip 파일을 복사 합니다.  Jsonlite 폴더를 추출 하 여% userprofile% \\ dearpackages에 복사 합니다. 이 단계에서는 R에 jsonlite 패키지를 자동으로 설치 합니다. 폴더 이름을 **jsonlite** 로 지정 해야 하며, 콘텐츠는 한 수준 아래에 있는 폴더에 직접 포함 되어야 합니다.</li><br><li>DEA를 닫고 다시 연 다음 분석을 다시 시도 합니다.</li><br>RGUI를 사용할 수도 있습니다. **packages**  >  **Zip에서 패키지 설치**로 이동 합니다. 이전에 다운로드 하 여 설치 하는 패키지로 이동 합니다.<br><br>RInterop를 초기화 하 고 올바르게 설정한 경우 RInterop 로그에 "dependent R package jsonlite 설치"가 표시 되어야 합니다.|  
|SQL Server 인스턴스에 연결할 수 없습니다. 서버 이름이 올바른지 확인 하 고 로그인 한 사용자에 대 한 필수 액세스 권한이 있는지 확인 하십시오.|서버에 대 한 액세스 권한이 나 사용자 권한이 없거나 서버 이름이 잘못 되었을 수 있습니다.|
|RInterop 프로세스 시간이 초과 되었습니다. DEA 및 RInterop 로그를 확인 하 고 작업 관리자에서 RInterop 프로세스를 중지 한 후 다시 시도 하십시오.<br><br>또는<br><br>RInterop가 오류가 발생 한 상태입니다. 작업 관리자에서 RInterop 프로세스를 중지 한 후 다시 시도 하십시오.|% Temp% \\ rinterop의 로그를 확인 하 여 오류를 확인 하십시오. 작업 관리자에서 RInterop 프로세스를 제거한 후 다시 시도 하십시오. 문제가 지속 되 면 제품 팀에 문의 하세요.|

**Q: 보고서가 생성 되었지만 데이터가 누락 된 것 같습니다.**

SQL Server를 실행 하 고 있는 분석 컴퓨터의 데이터베이스를 확인 하 여 데이터가 존재 하는지 확인 합니다. 분석 데이터베이스가 있는지 확인 하 고 해당 테이블을 확인 하십시오. 예를 들어 TblBatchesA, TblBatchesB 및 TblSummaryStats 테이블을 확인 합니다.

데이터가 없으면 데이터가 올바르게 복사 되지 않았거나 데이터베이스가 손상 되었을 수 있습니다. 일부 데이터만 누락 된 경우 캡처 또는 재생 시 생성 된 추적 파일에서 작업을 정확 하 게 캡처하지 못할 수 있습니다. 데이터가 있는 경우% temp% DEA의 로그 파일을 확인 하 여 \\ 오류가 기록 되었는지 확인 하십시오. 그런 다음, 다시 시도 하 여 분석 보고서를 생성 합니다.

추가 질문이 나 피드백이 있나요? 왼쪽 아래 모서리에서 웃는 얼굴 아이콘을 선택 하 여 DEA 도구를 통해 피드백을 제출 합니다.

## <a name="see-also"></a>참고 항목

- 분석 보고서를 보는 방법에 대 한 자세한 내용은 [보고서 보기](database-experimentation-assistant-view-report.md)를 참조 하세요.
