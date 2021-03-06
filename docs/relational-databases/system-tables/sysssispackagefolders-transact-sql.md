---
title: sysssispackagefolders (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdtspackagefolders90
- sysdtspackagefolders90_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysssispackagefolders system table
ms.assetid: ddc4833f-27bf-4610-b739-d257961d17ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c525b1b457c2bc9f505a83cc89a08a57c27e6279
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881278"
---
# <a name="sysssispackagefolders-transact-sql"></a>sysssispackagefolders(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  에서 사용 하는 폴더 계층 구조에 있는 각 논리적 폴더에 대해 하나의 행을 포함 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 합니다. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에 연결하면 이 폴더가 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]의 개체 탐색기에 나열됩니다. 폴더에는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 파일 시스템에 저장된 패키지가 나열됩니다.  
  
 **Parentfolderid** 열은 폴더 계층 구조를 설명 합니다. 폴더 계층 구조의 맨 위에 있는 폴더의 **parentfolderid**에 null 값이 포함 되어 있습니다.  
  
 **Foldername** 열에는 개체 탐색기에 표시 되는 폴더의 이름이 포함 됩니다.  
  
 이 테이블은 **msdb** 데이터베이스에 저장 됩니다.  

  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**folderid**|**uniqueidentifier**|폴더의 GUID입니다.|  
|**parentfolderid**|**uniqueidentifier**|부모 폴더의 GUID입니다.|  
|**foldername**|**sysname**|폴더 이름입니다. 이 이름은 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]의 폴더 계층 구조에 나타납니다.|  
  
  
