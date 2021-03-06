---
title: Filestream 및 FileTable 카탈로그 뷰 (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- FileTables [SQL Server], catalog views
ms.assetid: 2c83a4a7-720b-4435-a3b5-788c29f56949
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b9ff0596667be0822e2e65717ebfd757f001f821
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85764820"
---
# <a name="filestream-and-filetable-catalog-views-transact-sql"></a>Filestream 및 FileTable 카탈로그 뷰(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  이 섹션에서는 FileTable 기능과 관련된 카탈로그 뷰에 대해 설명합니다.  
  
## <a name="filestream-and-filetable-catalog-views-transact-sql"></a>Filestream 및 filetable 카탈로그 뷰 (Transact-sql)
 [sys.database_filestream_options&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql.md)  
 사용하도록 설정된 FileTable의 FILESTREAM 데이터에 대한 비트랜잭션 액세스 수준과 관련된 정보를 표시합니다. SQL Server 인스턴스의 각 데이터베이스마다 하나씩의 행을 포함합니다.  
  
 [sys.filetable_system_defined_objects&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql.md)  
 FileTable과 관련된 시스템 정의 개체의 목록을 표시합니다. 시스템 정의 개체마다 하나의 행을 포함합니다.  
  
 [sys.filetables&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-filetables-transact-sql.md)  
 FileTable마다 하나의 행을 반환합니다. 는 **sys. tables**에서 상속 됩니다.  

## <a name="see-also"></a>참고 항목
[Filestream](../../relational-databases/blob/filestream-sql-server.md)
<br>[Filetable](../../relational-databases/blob/filetables-sql-server.md)
<br>[Filestream 및 FileTable 동적 관리 뷰(Transact-SQL)](../system-dynamic-management-views/filestream-and-filetable-dynamic-management-views-transact-sql.md)
<br>[Filestream 및 FileTable 시스템 저장 프로시저(Transact-SQL)](../system-stored-procedures/filestream-and-filetable-system-stored-procedures.md)
  
  
