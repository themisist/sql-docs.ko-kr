---
title: BLOB 저장 옵션 비교(SQL Server) | Microsoft 문서
description: SQL Server는 Windows 애플리케이션에서 사용하는 Blob(Binary Large Object) 데이터를 저장할 수 있습니다. 조화되지 않은 데이터를 저장하기 위한 이 관계형 데이터베이스의 옵션을 비교합니다.
ms.custom: ''
ms.date: 03/04/2019
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 6038697b-36a9-49e8-a02a-2ad9e2e60e5a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b0faae244963957eadb1bd894f90a88736427b4
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85768059"
---
# <a name="compare-options-for-storing-blobs-sql-server"></a>BLOB 저장 옵션 비교(SQL Server)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 파일 및 문서를 저장하는 데 사용할 수 있는 옵션을 설명하고 비교합니다.

## <a name="storing-files-in-the-database---benefits-and-expectations"></a><a name="Expectations"></a> 데이터베이스에 파일 저장 - 이점 및 요구 사항

대부분의 기업 데이터는 본질적으로 구조화되어 있지 않으며 대개 파일 시스템에 파일 및 문서로 저장됩니다. 이러한 데이터는 대부분 Windows API를 통해 파일에 액세스하는 애플리케이션에서 생성, 관리 및 사용합니다. 일반적으로 기업에서는 이러한 데이터를 파일 시스템에 보관하는 한편, 파일의 관련 메타데이터는 관계형 데이터베이스에 저장합니다.

비정형 데이터를 관계형 데이터베이스에 통합하면 다음과 같은 이점을 얻을 수 있습니다.

- 백업과 같은 통합된 스토리지 및 데이터 관리 기능을 이용할 수 있습니다.
- 데이터 및 메타데이터에 대한 전체 텍스트 검색과 의미 체계 검색 같은 통합된 서비스를 이용할 수 있습니다.
- 구조화되지 않은 데이터에 대한 관리 및 정책 관리가 용이해집니다.

일반적으로 비정형 데이터를 관계형 데이터베이스에 저장하는 것이 불편했습니다. Microsoft Word 또는 Adobe Reader 같은 상용화된 애플리케이션을 관계형 데이터베이스 API를 통해 상호작용하도록 다시 작성하는 것은 실용적이지 않습니다. 이러한 애플리케이션은 Windows API를 통해 데이터에 액세스할 수 있어야 합니다. 애플리케이션에는 다음과 같은 기대 사항이 있습니다.

- Windows 애플리케이션에서는 데이터베이스 트랜잭션을 인식하지 않으며 그럴 필요도 없습니다.
- Windows 애플리케이션에서는 파일 및 디렉터리 데이터에 대한 파일 시스템 API와의 호환성이 필요합니다.

몇 년 전에 SQL Server는 비정형 데이터를 관계형 데이터베이스에 저장하는 다양한 방법을 제공하지 않았습니다. 하지만 지금은 비정형 데이터를 저장하는 방법을 제공합니다.

## <a name="filestream"></a><a name="Filestream"></a> FILESTREAM

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에 이미 FILESTREAM 기능이 있습니다. FILESTREAM 기능은 파일 시스템에 파일로 저장된 비정형 데이터를 효율적으로 스토리지, 관리 및 스트리밍할 수 있습니다. 그러나 FILESTREAM 솔루션은 사용자 지정 프로그래밍이 필요하며, 위에서 설명한 Windows 애플리케이션 호환성에 대한 요구 사항을 충족하지 않습니다.

## <a name="filetables"></a><a name="FileTables"></a> FileTable

FileTable 기능은 기존의 FILESTREAM 기술을 기반으로 빌드됩니다. FileTable 기능을 사용하면 기업 고객이 구조화되지 않은 파일 데이터와 디렉터리 계층 구조를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 저장할 수 있습니다. 이 기능은 파일 기반 데이터에 대한 비트랜잭션 액세스 및 Windows 애플리케이션 호환성에 대한 요구 사항을 해결합니다.

## <a name="comparing-filestream-and-filetable"></a><a name="CompareFileTable"></a> FILESTREAM 및 FileTable 비교

|기능|파일 서버 및 데이터베이스 솔루션|FILESTREAM 솔루션|FileTable 솔루션|
|:------|:--------------------------------|:------------------|:-----------------|
|**단일화된 관리 태스크**|예|예|**예**|
|**단일 서비스 집합**: 검색, 보고, 쿼리 등|예|예|**예**|
|**통합 보안 모델**|예|예|**예**|
|**FILESTREAM 데이터의 현재 위치 업데이트**|예|예|**예**|
|**파일 및 디렉터리 계층 구조를 데이터베이스에서 유지 관리**|예|예|**예**|
|**Windows 애플리케이션 호환성**|예|예|**예**|
|**파일 특성에 대한 관계형 액세스**|예|예|**예**|

## <a name="comparing-filestream-and-remote-blob-store-rbs"></a><a name="CompareRBS"></a> FILESTREAM 및 RBS(Remote BLOB Store) 비교

비정형 데이터를 저장하는 또 다른 옵션에는 RBS(원격 BLOB 저장소)가 포함됩니다. 자세한 내용은 [RBS(원격 Blob 저장소)(SQL Server)](remote-blob-store-rbs-sql-server.md)를 참조하세요.

## <a name="more-information"></a><a name="more"></a> 자세한 정보

[FILESTREAM&#40;SQL Server&#41;](../../relational-databases/blob/filestream-sql-server.md)  
[FileTables&#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md)  
[RBS&#40;Remote Blob Store&#41;&#40;SQL Server&#41;](../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)
