---
title: SqlServiceType 속성 (Sqlservicetype)
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- SqlServiceType Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6818c721d6f555ea2cf8e03aa7ed664fe10c04cd
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85888332"
---
# <a name="sqlservicetype-property-sqlservice-class"></a>SqlServiceType 속성(SqlService 클래스)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  관리되는 서비스의 유형을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.SqlServiceType [= value]  
```  
  
## <a name="parts"></a>부분  
 *object*  
 서비스를 나타내는 [SqlService 클래스](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) 개체입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 서비스 유형을 지정하는 uint32 값입니다.  
  
## <a name="remarks"></a>설명  
 반환 값은 다음 중 하나일 수 있습니다.  
  
|유형|정의|  
|----------|----------------|  
|*1*|MSSQLSERVER는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 서비스입니다.|  
|*2*|SQLSERVERAGENT는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 에이전트 서비스입니다.|  
|*3*|MSFTESQL은 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 전체 텍스트 검색 엔진 서비스입니다.|  
|*4*|MsDtsServer는 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 서비스입니다.|  
|*5*|MSSQLServerOLAPService는 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 서비스입니다.|  
|*6*|ReportServer는 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 서비스입니다.|  
|*7*|SQLBrowser는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser 서비스입니다.|  
|*8*|NsService는 [!INCLUDE[ssNoVersion](../../../includes/ssns-md.md)] 알림 서비스입니다.|  
|*9*|MSSQLFDLauncher는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 전체 텍스트 필터 데몬 시작 관리자 서비스입니다.|  
|*10*|SQLPBENGINE은 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Polybase 엔진 서비스입니다.|  
|*11*|SQLPBDMS는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Polybase 데이터 이동 서비스입니다.|  
|*12*|MSSQLLaunchpad는 실행 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 패드 서비스입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [서비스 시작 및 중지](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
