---
title: '자습서: R에서 클러스터링 모델 개발'
titleSuffix: SQL Machine Learning
description: 4부로 구성된 이 자습서 시리즈에서는 R에서 SQL 기계 학습을 사용하여 클러스터링을 수행하는 모델을 개발합니다.
ms.prod: sql
ms.technology: machine-learning
ms.topic: tutorial
author: cawrites
ms.author: chadam
ms.reviewer: garye, davidph
ms.date: 05/04/2020
ms.custom: seo-lt-2019
monikerRange: '>=sql-server-2016||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 558d6b9aaa47288de7c75e61ee38d379a3fc1e68
ms.sourcegitcommit: dc965772bd4dbf8dd8372a846c67028e277ce57e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83607106"
---
# <a name="tutorial-prepare-data-to-perform-clustering-in-r-with-sql-machine-learning"></a>자습서: R에서 SQL 기계 학습을 사용하여 클러스터링을 수행하기 위한 데이터 준비

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
4부로 구성된 이 자습서 시리즈에서는 고객 데이터를 분류하기 위해 R을 사용하여 [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) 또는 [빅 데이터 클러스터](../../big-data-cluster/machine-learning-services.md)에서 K-평균 클러스터링 모델을 개발하고 배포합니다.
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
4부로 구성된 이 자습서 시리즈에서는 고객 데이터를 클러스터링하기 위해 [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md)에서 R을 사용하여 K-평균 클러스터링 모델을 개발 및 배포합니다.
::: moniker-end
::: moniker range="=sql-server-2016||=sqlallproducts-allversions"
4부로 구성된 이 자습서 시리즈에서는 고객 데이터를 클러스터링하기 위해 [SQL Server R Services](../r/sql-server-r-services.md)에서 R을 사용하여 K-평균 클러스터링 모델을 개발 및 배포합니다.
::: moniker-end

이 시리즈의 1부에서는 자습서의 사전 요구 사항을 설치한 다음, 샘플 데이터 세트를 데이터베이스에 복원합니다. 2부 및 3부에서는 데이터를 분석 및 준비하고 기계 학습 모델을 학습시키기 위해 Azure Data Studio Notebook에서 일부 R 스크립트를 개발합니다. 그런 다음, 4부에서는 데이터베이스 내부에서 저장 프로시저를 사용하여 R 스크립트를 실행합니다.

*클러스터링*은 그룹 구성원이 일정 기준에 따라 유사한 특성을 갖는 그룹으로 데이터를 정리하는 것과 같습니다. 이 자습서 시리즈에서는 사용자가 판매점을 소유하고 있다고 가정합니다. **K-평균** 알고리즘을 사용하여 제품 구매 및 반품 데이터 세트에서 고객에 대한 클러스터링을 수행합니다. 고객을 클러스터링하면 특정 그룹을 대상으로 보다 효과적으로 마케팅 노력을 집중할 수 있습니다. K-평균 클러스터링은 유사성을 기준으로 데이터의 패턴을 찾는 *자율 학습* 알고리즘입니다.


이 문서에서는 다음을 수행하는 방법을 알아봅니다.

> [!div class="checklist"]
> * 샘플 데이터베이스 복원
> 
[2부](r-clustering-model-prepare-data.md)에서는 클러스터링을 수행하기 위해 데이터베이스의 데이터를 준비하는 방법을 알아봅니다.

[3부](r-clustering-model-build.md)에서는 R에서 K-평균 클러스터링 모델을 만들고 학습시키는 방법을 알아봅니다.

[4부](r-clustering-model-deploy.md)에서는 새 데이터를 기준으로 R에서 클러스터링을 수행할 수 있는 저장 프로시저를 데이터베이스에서 만드는 방법을 알아봅니다.

## <a name="prerequisites"></a>사전 요구 사항

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
* [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) 및 Python 언어 옵션 - [Windows 설치 가이드](../install/sql-machine-learning-services-windows-install.md) 또는 [Linux 설치 가이드](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-machine-learning?toc=%2fsql%2fmachine-learning%2ftoc.json&view=sql-server-linux-ver15)의 설치 지침을 따릅니다. [SQL Server 빅 데이터 클러스터에서 Machine Learning Services를 사용하도록 설정](../../big-data-cluster/machine-learning-services.md)할 수도 있습니다.
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
* [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) 및 R 언어 옵션 - [Windows 설치 가이드](../install/sql-machine-learning-services-windows-install.md)의 설치 지침을 따릅니다.
::: moniker-end

* [Azure Data Studio](../../azure-data-studio/what-is.md) SQL용 Azure Data Studio에서 Notebook을 사용합니다. Notebook에 대한 자세한 내용은 [Azure Data Studio에서 Notebook을 사용하는 방법](../../azure-data-studio/notebooks-guidance.md)을 참조하세요.

* R IDE - 이 자습서에서는 [RStudio Desktop](https://www.rstudio.com/products/rstudio/download/)을 사용합니다.

* RODBC - 이 드라이버는 이 자습서에서 개발할 R 스크립트에 사용됩니다. 아직 설치하지 않았으면 R 명령 `install.packages("RODBC")`를 사용하여 설치합니다. RODBC에 대한 자세한 내용은 [CRAN - Package RODBC](https://CRAN.R-project.org/package=RODBC)를 참조하세요.

## <a name="restore-the-sample-database"></a>샘플 데이터베이스 복원

이 자습서에 사용되는 샘플 데이터 세트는 **.bak** 데이터베이스 백업 파일로 저장되었으며, 사용자가 다운로드하여 사용할 수 있습니다. 이 데이터 세트는 [Transaction Processing Performance Council(TPC)](http://www.tpc.org/default.asp)에서 제공되는 [tpcx-bb](http://www.tpc.org/tpcx-bb/default.asp) 데이터 세트에서 파생됩니다.

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
> [!NOTE]
> 빅 데이터 클러스터에서 Machine Learning Services를 사용하는 경우 [SQL Server 빅 데이터 클러스터 마스터 인스턴스에 데이터베이스 복원](../../big-data-cluster/data-ingestion-restore-database.md)을 참조하세요.
::: moniker-end

1. [tpcxbb_1gb.bak](https://sqlchoice.blob.core.windows.net/sqlchoice/static/tpcxbb_1gb.bak) 파일을 다운로드하세요.

1. Azure Data Studio에서 다음 세부 정보를 사용하여 [백업 파일에서 데이터베이스 복원](../../azure-data-studio/tutorial-backup-restore-sql-server.md#restore-a-database-from-a-backup-file)의 지침을 따릅니다.

   * 다운로드한 **tpcxbb_1gb.bak** 파일에서 가져옵니다.
   * 대상 데이터베이스 이름을 "tpcxbb_1gb"로 지정합니다.

1. **dbo.customer** 테이블을 쿼리하여 데이터베이스를 복원한 후 데이터 세트가 존재하는지 확인할 수 있습니다.

    ```sql
    USE tpcxbb_1gb;
    SELECT * FROM [dbo].[customer];
    ```

## <a name="clean-up-resources"></a>리소스 정리

이 자습서를 계속 진행할 생각이 없으면 tpcxbb_1gb 데이터베이스를 삭제하세요.

## <a name="next-steps"></a>다음 단계

이 자습서 시리즈의 1부에서 다음 단계를 완료했습니다.

* 필수 구성 요소 설치
* 샘플 데이터베이스를 SQL Server에 복원함

Machine Learning 모델을 위해 데이터를 준비하려면 이 자습서 시리즈의 2부를 진행합니다.

> [!div class="nextstepaction"]
> [클러스터링을 수행할 데이터 준비](r-clustering-model-prepare-data.md)
