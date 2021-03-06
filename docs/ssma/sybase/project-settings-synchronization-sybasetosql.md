---
title: 프로젝트 설정 (동기화) (SybaseToSQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 2cd6bc01-b8e5-4312-83a4-eac66dc1d460
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 663a4b1e49d1f81ce040254a2c8f39a1a1f84b38
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68028677"
---
# <a name="project-settings-synchronization-sybasetosql"></a>프로젝트 설정(동기화)(SybaseToSQL)
**프로젝트 설정** 대화 상자의 동기화 페이지에는 테이블 및 저장 프로시저와 같은 데이터베이스 개체를 또는 SQL Azure로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로드 하는 방법을 사용자 지정 하는 설정이 포함 되어 있습니다.  
  
동일한 설정을 포함 하는 두 개의 서로 다른 동기화 페이지에 액세스할 수 있습니다.  
  
-   모든 향후 SSMA 프로젝트에 대 한 설정을 지정 하려면 **도구** 메뉴에서 **기본 프로젝트 설정**을 선택 하 고 마이그레이션 **대상 버전** 드롭다운에서 설정 하거나 변경 해야 하는 설정에 대 한 마이그레이션 프로젝트 형식을 선택한 다음 왼쪽 창의 맨 아래에서 **동기화** 를 선택 합니다.  
  
-   현재 프로젝트에 대 한 설정을 지정 하려면 **도구** 메뉴에서 **프로젝트 설정**을 선택 하 고 왼쪽 창의 맨 아래에서 **동기화** 를 선택 합니다.  
  
## <a name="options"></a>옵션  
**시도한**  
에서 개체를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]로드할 때의 시도 횟수를 지정 합니다. 현재 시도에서로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로드 되지 않은 개체는 ssma가 현재 동기화 프로세스의 최대 시도 수에 도달할 때까지 다시 시도 됩니다.  
  
## <a name="synchronization-for-sql-server"></a>SQL Server에 대 한 동기화  
**로컬 및 원격 개체 변경에서 로컬 개체 새로 고침**  
로컬 및 원격 개체가 모두 변경 되는 경우 SSMA에서 로컬 개체 메타 데이터를 원격 개체 메타 데이터로 바꿀지 여부를 지정 합니다.  
**데이터베이스에서 새로 고침**을 선택 하는 경우 ssma는 조건이 충족 될 때 메타 데이터에 데이터베이스 정의를 로드 합니다.  
**데이터베이스에 쓰기**를 선택 하는 경우 ssma는 조건이 충족 될 때 ssma 메타 데이터 내용에 따라 데이터베이스의 개체를 업데이트 합니다.  
**건너뛰기**를 선택 하면 ssma는 새로 고침 작업을 수행 하지 않습니다.   
기본 옵션 집합이 **데이터베이스에 쓰기입니다.**  
  
**로컬 개체 변경 시 로컬 개체 새로 고침**  
원격 개체가 변경 되는 경우 SSMA에서 로컬 개체 메타 데이터를 원격 개체 메타 데이터로 바꿀지 여부를 지정 합니다.  
**데이터베이스에서 새로 고침**을 선택 하는 경우 ssma는 조건이 충족 될 때 메타 데이터에 데이터베이스 정의를 로드 합니다.  
**데이터베이스에 쓰기**를 선택 하는 경우 ssma는 조건이 충족 될 때 ssma 메타 데이터 내용에 따라 데이터베이스의 개체를 업데이트 합니다.  
**건너뛰기**를 선택 하면 ssma는 새로 고침 작업을 수행 하지 않습니다.   
기본 옵션 집합이 **데이터베이스에 쓰기**입니다.  
  
**원격 개체 변경 시 로컬 개체 새로 고침**  
원격 개체가 변경 되는 경우 SSMA에서 로컬 개체 메타 데이터를 원격 개체 메타 데이터로 바꿀지 여부를 지정 합니다.  
**데이터베이스에서 새로 고침**을 선택 하는 경우 ssma는 조건이 충족 될 때 메타 데이터에 데이터베이스 정의를 로드 합니다.  
**데이터베이스에 쓰기**를 선택 하는 경우 ssma는 조건이 충족 될 때 ssma 메타 데이터 내용에 따라 데이터베이스의 개체를 업데이트 합니다.  
**건너뛰기**를 선택 하면 ssma는 새로 고침 작업을 수행 하지 않습니다.   
기본 옵션 집합이 **데이터베이스에서 새로 고침**입니다.  
  
**로컬 개체 메타 데이터가 없는 경우 새로 고침**  
대상 데이터베이스에 개체가 있지만 로컬에는 없는 경우 SSMA에서 로컬 메타 데이터를 만들지 여부를 지정 합니다.  
**데이터베이스에서 새로 고침**을 선택 하는 경우 ssma는 조건이 충족 될 때 데이터베이스에서 새로 고침 옵션을 선택 합니다.  
**데이터베이스에 쓰기**를 선택 하는 경우 ssma는 조건이 충족 될 때 데이터베이스에서 개체를 삭제 합니다.  
**건너뛰기**를 선택 하면 ssma는 새로 고침 작업을 수행 하지 않습니다.   
기본 옵션 집합이 **데이터베이스에서 새로 고침**입니다.  
  
