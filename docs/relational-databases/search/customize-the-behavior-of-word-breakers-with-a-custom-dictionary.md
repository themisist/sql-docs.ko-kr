---
title: 사용자 지정 사전을 사용하여 단어 분리기의 동작 사용자 지정
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: search, sql-database
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.custom: seo-lt-2019
ms.openlocfilehash: d9a3f034312dcb6be52534968034fe526cfa5955
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85758061"
---
# <a name="customize-behavior-of-word-breakers-with-a-custom-dictionary-sql-server-search"></a>사용자 지정 사전을 사용하여 단어 분리기의 동작 사용자 지정(SQL Server 검색)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  언어별 사용자 지정 사전 파일을 만들어 특정 언어에 대한 단어 분리기 동작을 사용자 지정할 수 있습니다. 예를 들어 단어 분리기에서 특정 용어 또는 패턴을 분리하지 못하도록 차단할 수 있습니다.  
  
 자세한 내용은 다음 SharePoint 문서를 참조하십시오.  
  
 [사용자 지정 사전 만들기(SharePoint Server 2010)](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 사용자 지정 사전 파일을 다음 폴더에 배치합니다.  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 사용자 지정 사전 파일을 만들거나 변경한 후 다음 명령을 사용하여 SQL 전체 텍스트 데몬 시작 관리자를 다시 시작합니다.  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
