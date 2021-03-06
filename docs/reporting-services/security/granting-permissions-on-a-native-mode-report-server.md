---
title: 기본 모드 보고서 서버에 대한 권한 부여 | Microsoft Docs
ms.date: 05/14/2019
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- authorization [Reporting Services]
- server security [Reporting Services]
- role-based security [Reporting Services]
- items [Reporting Services], security
- permissions [Reporting Services], native mode
- published reports [Reporting Services], security
- reports [Reporting Services], security
- report items [Reporting Services], security
- role-based security [Reporting Services], about role-based security
- security [Reporting Services], role-based
ms.assetid: 260dc2e9-546c-4f04-9fa1-977e23c9d68c
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: be6b0825244dee9f80f88a1b211eee5881d2a96a
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "77147373"
---
# <a name="grant-permissions-on-a-native-mode-report-server"></a>기본 모드 보고서 서버에 대한 권한 부여
  SQL Server [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 에서는 역할 기반 권한 부여 및 인증 하위 시스템을 통해 보고서 서버에서 작업을 수행하거나 항목에 액세스할 수 있는 사용자를 지정합니다. 역할 기반 권한 부여는 사용자 또는 그룹이 수행할 수 있는 동작을 역할별로 분류합니다. 인증은 기본 제공 Windows 인증이나 사용자가 제공하는 사용자 지정 인증 모듈을 기반으로 합니다. 이러한 인증 유형 중 하나에 미리 정의된 역할이나 사용자 지정 역할을 사용할 수 있습니다.
  
## <a name="use-roles-to-grant-report-server-access"></a>역할을 사용하여 보고서 서버 액세스 권한 부여
 모든 사용자는 특정 액세스 수준을 정의하는 역할의 컨텍스트 내에서 보고서 서버와 상호 작용합니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 에는 보고서 서버에 즉시 액세스하도록 사용자 및 그룹에 할당할 수 있는 미리 정의된 역할이 포함되어 있습니다. 미리 정의된 역할에는 **콘텐츠 관리자**, **게시자**, **브라우저** 등이 있습니다. 각 역할은 관련 태스크 모음을 정의합니다. 예를 들어 **게시자** 는 보고서를 추가하고 이러한 보고서를 저장하는 데 사용할 폴더를 만들 수 있는 권한을 갖습니다.
  
 역할 할당은 일반적으로 부모 노드로부터 상속되지만 특정 항목에 대한 새 역할 할당을 만들어서 사용 권한 상속을 해제할 수 있습니다. 한 보고서의 **콘텐츠 관리자** 역할 멤버인 사용자가 다른 보고서의 **브라우저** 역할 멤버가 될 수 있습니다.
  
 보고서 서버 항목 및 작업에 대한 액세스 권한을 부여하려면:
  
1. 미리 정의된 역할을 검토하여 이를 그대로 사용할 수 있는지 확인합니다. 작업을 조정하거나 추가 역할을 정의해야 하는 경우 특정 역할에 사용자를 할당하기 전에 다음 작업을 수행합니다. 각 역할에 대한 자세한 내용은 [미리 정의된 역할](../../reporting-services/security/role-definitions-predefined-roles.md)을 참조하세요.
  
1. 보고서 서버에 대한 액세스 권한이 필요한 사용자 및 그룹과 필요한 수준을 확인합니다. **브라우저** 역할 또는 **보고서 작성기** 역할에 대부분의 사용자를 할당합니다. **게시자** 역할에 더 적은 수의 사용자를 할당합니다. **콘텐츠 관리자** 역할에 소수의 사용자만 할당합니다.
  
1. 웹 포털을 사용하여 홈 폴더에 대한 액세스 권한을 필요로 하는 각 사용자 또는 그룹에 대해 역할을 할당합니다. 홈 폴더는 보고서 서버 폴더 계층 구조의 최상위 폴더입니다.
  
1. 웹 포털에 있는 **사이트 설정** 페이지의 사이트 수준에서 미리 정의된 **시스템 사용자** 및 **시스템 관리자** 역할을 사용하여 각 사용자 및 그룹에 대한 시스템 수준 역할 할당을 만듭니다.
  
1. 특정 폴더, 보고서 및 기타 항목에 대한 추가 역할 할당을 필요한 만큼 만듭니다. 역할 할당을 너무 많이 만들지는 마십시오. 너무 많이 만들면 각 사용자의 여러 권한 수준을 추적하기 어렵습니다.
  
> [!NOTE]  
>  SharePoint 통합 모드에서 실행되도록 보고서 서버를 구성한 경우 보고서 서버 항목에 대한 액세스 권한을 부여하려면 SharePoint 사이트에 대한 사용 권한을 설정해야 합니다. 자세한 내용은 [SharePoint 사이트의 보고서 서버 항목에 대한 권한 부여](../../reporting-services/security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md)를 참조하세요.
> 
> SQL Server 2016 이후부터 SharePoint와의 Reporting Services 통합을 사용할 수 없습니다.
  
## <a name="who-sets-permissions"></a>권한 설정의 주체
 기본적으로 로컬 관리자 그룹의 멤버인 사용자만 보고서 서버에 액세스할 수 있습니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 는 로컬 관리자 그룹 멤버에게 항목 수준 및 시스템 수준 액세스 권한을 부여하는 두 개의 기본 역할 할당과 함께 설치됩니다. 로컬 관리자는 이 기본 제공 역할 할당을 사용하여 다른 사용자에게 보고서 서버 액세스 권한을 부여하고 보고서 서버 항목을 관리할 수 있습니다. 기본 제공 역할 할당은 삭제할 수 없습니다. 로컬 관리자는 항상 보고서 서버 인스턴스를 완전히 관리할 수 있는 권한을 가집니다.
 
 사용자가 Windows Vista 또는 Windows Server 2008을 실행하는 로컬 컴퓨터에서 보고서 서버 인스턴스를 관리하려면 추가 구성이 필요합니다. 자세한 내용은 [로컬 관리에 대해 기본 모드 보고서 서버 구성&#40;SSRS&#41;](../../reporting-services/report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md)을 참조하세요.
  
## <a name="how-permissions-are-stored"></a>권한 저장 방식
 역할 할당 및 정의는 보고서 서버 데이터베이스에 저장됩니다. 여러 개의 클라이언트 도구나 프로그래밍 인터페이스를 사용하는 경우 모든 액세스에는 보고서 서버 인스턴스에 대해 전체적으로 정의된 권한이 필요합니다. 스케일 아웃 배포에 다중 보고서 서버를 구성하는 경우 한 인스턴스에 정의하는 역할 할당은 공유 데이터베이스에 저장되어 동일한 스케일 아웃 배포에 있는 다른 모든 인스턴스에 사용됩니다. 역할 할당은 보안을 설정하는 항목과 함께 저장되므로 사용자가 정의한 권한을 잃지 않고도 데이터베이스를 다른 보고서 서버 인스턴스로 이동할 수 있습니다.
  
## <a name="tasks-and-tools-for-managing-permissions"></a>권한 관리에 사용되는 작업 및 도구
 다음 도구를 사용하여 역할 정의 및 할당을 관리할 수 있습니다.
  
|도구|작업|  
|----------|-----------|  
|Management Studio: 역할 정의를 확인, 수정, 작성 및 삭제하는 데 사용됩니다.|[역할 만들기, 삭제 또는 수정&#40;Management Studio&#41;](../../reporting-services/security/role-definitions-create-delete-or-modify.md)|  
|웹 포털: 역할에 사용자 및 그룹을 할당하는 데 사용됩니다.|[보고서 서버에 사용자 액세스 권한 부여](../../reporting-services/security/grant-user-access-to-a-report-server.md)<br /><br /> [역할 할당 수정 또는 삭제](../../reporting-services/security/role-assignments-modify-or-delete.md)|  
  
## <a name="see-also"></a>참고 항목
 - [미리 정의된 역할](../../reporting-services/security/role-definitions-predefined-roles.md)  
 - [SharePoint 사이트의 보고서 서버 항목에 대한 권한 부여](../../reporting-services/security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 - [보고서 서버 인증](../../reporting-services/security/authentication-with-the-report-server.md)  
 - [역할 할당 만들기 및 관리](../../reporting-services/security/create-and-manage-role-assignments.md)  
 - [Reporting Services 보안 및 보호](../../reporting-services/security/reporting-services-security-and-protection.md)  
 - [보고서 서버 콘텐츠 관리&#40;SSRS 기본 모드&#41;](../../reporting-services/report-server/report-server-content-management-ssrs-native-mode.md)  
  
  
