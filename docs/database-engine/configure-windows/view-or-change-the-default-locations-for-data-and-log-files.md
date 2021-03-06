---
title: 데이터 및 로그 파일의 기본 위치 보기 또는 변경 | Microsoft Docs
description: SQL Server 데이터 파일 및 로그 파일의 기본 위치를 보거나 변경하는 방법을 알아봅니다. ACL(액세스 제어 목록)을 사용하여 파일을 보호하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 9a0c720684f0eefa301e9a5387ffda54e349f85d
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85680787"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files"></a>데이터 및 로그 파일의 기본 위치 보기 또는 변경
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
 데이터 파일 및 로그 파일을 보호하는 최선의 방법은 ACL(액세스 제어 목록)로 보호하는 것입니다. 파일을 만든 위치의 루트 디렉터리에 ACL을 설정합니다.  
 
  
## <a name="view-or-change-the-default-locations-for-database-files"></a>데이터베이스 파일의 기본 위치를 보거나 변경  
  
1.  개체 탐색기에서 서버를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
2.  속성 페이지의 왼쪽 패널에서 **데이터베이스 설정** 탭을 클릭합니다.  
  
3.  **데이터베이스 기본 위치**에서 새 데이터 파일 및 새 로그 파일의 현재 기본 위치를 봅니다. 기본 위치를 변경하려면 **데이터** 또는 **로그** 필드에 새 기본 경로 이름을 입력하거나 찾아보기 단추를 클릭한 다음 경로 이름을 찾아 선택합니다.  
  
>**참고:** 기본 위치를 변경한 후 변경 내용을 적용하려면 SQL Server 서비스를 중지했다가 시작해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CREATE DATABASE&#40;SQL Server Transact-SQL&#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md)   
 [데이터베이스 만들기](../../relational-databases/databases/create-a-database.md)  
  
  
