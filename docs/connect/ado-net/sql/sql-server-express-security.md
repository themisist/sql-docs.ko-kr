---
title: SQL Server Express 보안
description: SQL Server Express의 보안 고려 사항에 대해 설명합니다.
ms.date: 09/26/2019
ms.assetid: cf9cf6d9-4b05-43e9-ac7b-6cefbfcd6d4e
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daenge
ms.reviewer: v-kaywon
ms.openlocfilehash: 0e9a0b87e0275846b1c1b9535b9485dd1cbae066
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243427"
---
# <a name="sql-server-express-security"></a>SQL Server Express 보안

[!INCLUDE[Driver_ADONET_Download](../../../includes/driver_adonet_download.md)]

Microsoft SQL Server Express Edition(SQL Server Express)은 Microsoft SQL Server 기반으로 하며 대부분의 데이터베이스 엔진 기능을 지원합니다. 필요하지 않은 기능 및 네트워크 연결은 기본적으로 해제되어 있습니다. 이렇게 하면 악의적인 사용자가 공격에 이용할 수 있는 노출 영역을 줄일 수 있습니다.  
  
SQL Server Express는 일반적으로 명명된 인스턴스로 설치됩니다. 기본 인스턴스 이름은 `SQLExpress`입니다. 명명된 인스턴스는 설치하는 동안 지정한 인스턴스 이름과 컴퓨터의 네트워크 이름으로 식별됩니다.  
  
## <a name="network-access"></a>네트워크 액세스  
보안상의 이유로 SQL Server Express에서 네트워킹 프로토콜은 기본적으로 비활성 상태입니다. 이는 SQL Server Express 인스턴스를 호스트하는 컴퓨터를 손상시킬 수 있는 외부 사용자의 공격을 방지합니다. 네트워크 연결을 명시적으로 사용하도록 설정하고 SQL Server Browser 서비스를 시작하여 다른 컴퓨터에서 SQL Server Express 인스턴스에 연결해야 합니다.  
  
네트워크 연결을 사용하도록 설정하면 SQL Server Express 인스턴스는 SQL Server의 다른 버전과 동일한 보안 요구 사항을 갖습니다.  
  
## <a name="user-instances"></a>사용자 인스턴스  
사용자 인스턴스는 SQL Server Express의 부모 인스턴스에서 생성되는 SQL Server Express 데이터베이스 엔진의 개별 인스턴스입니다. 사용자 인스턴스의 기본 목표는 최소 권한 사용자 계정으로 Windows를 실행하는 사용자가 로컬 컴퓨터의 SQL Server Express 인스턴스에 대해 시스템 관리자(`sysadmin`) 권한을 갖도록 허용하는 것입니다. 사용자 인스턴스는 시스템 관리자인 사용자가 자신의 컴퓨터에서 사용하기 위한 것이 아닙니다.  
  
사용자 인스턴스는 사용자를 대신하여 SQL Server 또는 SQL Server Express의 기본 인스턴스에서 생성됩니다. 사용자의 Windows 보안 컨텍스트에서 서비스가 아니라 사용자 프로세스로 실행됩니다. SQL Server 로그인은 허용되지 않습니다. Windows 로그인만 지원됩니다. 이렇게 하면 사용자 인스턴스에서 실행되는 소프트웨어가 사용자에게 부여된 권한이 없는 시스템 차원 변경 작업을 수행할 수 없습니다. 사용자 인스턴스는 자식 또는 클라이언트 인스턴스라고도 하며, 때로는 머리글자어 RANU("일반 사용자로 실행")를 사용하여 참조됩니다.  
  
각 사용자 인스턴스는 부모 인스턴스 및 동일한 컴퓨터에서 실행되는 다른 사용자 인스턴스로부터 격리됩니다. 사용자 인스턴스에 설치된 데이터베이스는 단일 사용자 모드로만 열립니다. 여러 사용자가 연결할 수는 없습니다. 사용자 인스턴스에 대해 복제, 분산 쿼리 및 원격 연결을 사용할 수 없습니다. 사용자 인스턴스에 연결된 경우 사용자에게는 부모 SQL Server Express 인스턴스에 대한 특별한 권한이 없습니다.  
  
## <a name="external-resources"></a>외부 리소스  
SQL Server Express에 대한 자세한 내용은 다음 리소스를 참조하세요.  
  
|리소스|설명|
|-|-|  
|[Microsoft SQL Server 2005 Express Edition 온라인 설명서](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms165706(v=sql.90))|SQL Server 2005 Express Edition에 대한 전체 설명서입니다.|  
|[비관리자용 사용자 인스턴스](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms143684(v=sql.100))(SQL Server 온라인 설명서)|사용자 인스턴스를 만들고 배포하는 방법을 설명합니다.|  
|[SQL Server Express 사용자 인스턴스](sql-server-express-user-instances.md)|ADO.NET 애플리케이션의 사용자 인스턴스 기능에 대해 설명합니다. 사용자 인스턴스를 사용하도록 설정하는 방법, <xref:Microsoft.Data.SqlClient.SqlConnection>을 사용하여 사용자 인스턴스에 연결하는 방법, 사용자 인스턴스 수명, 사용자 인스턴스 시나리오에 대한 정보를 제공합니다.|  
  
## <a name="next-steps"></a>다음 단계
- [SQL Server 보안](sql-server-security.md)
- [SQL Server Express 사용자 인스턴스](sql-server-express-user-instances.md)
