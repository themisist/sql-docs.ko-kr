---
title: Filestream 및 FileTable 동적 관리 뷰 (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- FileTables [SQL Server], dynamic management views
ms.assetid: e50a135d-6644-42a4-a0df-1c7a2b722051
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 782885ddccf486cb74b0b79b60422f1564d4ddbc
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85894683"
---
# <a name="filestream-and-filetable-dynamic-management-views-transact-sql"></a>Filestream 및 FileTable 동적 관리 뷰(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  이 섹션에서는 FILESTREAM 및 FileTable 기능과 관련된 동적 관리 뷰에 대해 설명합니다.  
  
## <a name="filestream-dynamic-management-views-and-functions"></a>Filestream 동적 관리 뷰 및 함수  
 [sys.dm_filestream_file_io_handles&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql.md)  
 현재 열려 있는 트랜잭션 파일 핸들을 표시합니다.  
  
 [sys.dm_filestream_file_io_requests&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql.md)  
 현재 파일 입력 및 파일 출력 요청을 표시합니다.  
  
## <a name="filetable-dynamic-management-views-and-functions"></a>FileTable 동적 관리 뷰 및 함수  
 [sys.dm_filestream_non_transacted_handles&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql.md)  
 FileTable 데이터에 대한 현재 열려 있는 비트랜잭션 파일 핸들을 표시합니다.  

## <a name="see-also"></a>참고 항목
[Filestream](../../relational-databases/blob/filestream-sql-server.md)
<br>[Filetable](../../relational-databases/blob/filetables-sql-server.md)
<br>[Filestream 및 FileTable 카탈로그 뷰(Transact-SQL)](../system-catalog-views/filestream-and-filetable-catalog-views-transact-sql.md)
<br>[Filestream 및 FileTable 시스템 저장 프로시저(Transact-SQL)](../system-stored-procedures/filestream-and-filetable-system-stored-procedures.md)
  
