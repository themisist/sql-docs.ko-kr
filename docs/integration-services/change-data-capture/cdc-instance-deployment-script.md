---
title: CDC 인스턴스 배포 스크립트 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34e5b1872c23d28a59ae0a9ac762c470fc297ee0
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86921198"
---
# <a name="cdc-instance-deployment-script"></a>CDC 인스턴스 배포 스크립트

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  CDC 인스턴스 배포 스크립트를 표시하는 CDC 인스턴스 배포 스크립트 대화 상자입니다. 이 스크립트를 사용하여 다른 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스의 모든 아티팩트를 포함하는 CDC 데이터베이스를 다시 만들 수 있습니다.  
  
 배포 스크립트가 완료되면 다음을 확인해야 합니다.  
  
-   배포 스크립트에서는 Oracle CDC Service 구성 콘솔 또는 프로그램에서 만들어지는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 준비 스크립트 **를 사용하여 대상** 인스턴스가 Oracle CDC에 사용할 수 있도록 준비된 것으로 간주합니다.  
  
-   CDC에 데이터베이스를 사용하도록 설정하는 데 사용되는 스크립트 부분을 `sysadmin`이 실행해야 합니다.  
  
-   이 스크립트는 Oracle 로그 마이닝 암호를 유지하지 않습니다. 스크립트가 실행되고 Oracle CDC Service가 시작된 후에 암호를 수동으로 설정해야 합니다.  
  
 **CDC 인스턴스 배포 스크립트** 대화 상자에서 다음 옵션을 선택합니다.  
  
 **다른 이름으로 저장**  
 원하는 위치에 저장할 수 있는 텍스트 파일로 스크립트를 저장합니다. 스크립트를 포함하는 파일을 다른 서버에 복사하여 해당 서버에서 실행할 수 있습니다.  
  
 **Copy**  
 스크립트를 클립보드에 복사합니다. 그런 다음 스크립트를 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 또는 텍스트 편집기에 붙여넣어 나중에 실행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDC를 위한 SQL Server 준비](../../integration-services/change-data-capture/prepare-sql-server-for-cdc.md)  
  
  
