---
title: ORIGINAL_DB_NAME(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- ORIGINAL_DB_NAME
- ORIGINAL_DB_NAME_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ORIGINAL_DB_NAME function
ms.assetid: 7dadc40a-1287-4f31-8487-434ee477144d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 889cdb18a323e64cf1b94bcde57eaf77c37e89d4
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85892555"
---
# <a name="original_db_name-transact-sql"></a>ORIGINAL_DB_NAME(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  사용자가 데이터베이스 연결 문자열에 지정한 데이터베이스 이름을 반환합니다. 이 데이터베이스는 **sqlcmd-d** 옵션(USE *database*)을 사용하여 지정됩니다. ODBC(Open Database Connectivity) 데이터 원본 식(initial catalog = *databasename*)을 사용하여 지정할 수도 있습니다.  
  
 이 데이터베이스는 기본 사용자 데이터베이스와 다릅니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
ORIGINAL_DB_NAME ()  
```  
  
## <a name="remarks"></a>설명  
 초기 데이터베이스가 지정되지 않으면 함수는 빈 문자열을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [sqlcmd 유틸리티](../../tools/sqlcmd-utility.md)   
 [osql Utility](../../tools/osql-utility.md)   
 [SQL Server Native Client(ODBC)](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
