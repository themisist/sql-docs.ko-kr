---
title: sys.sysoledbusers (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sysoledbusers
- sys.sysoledbusers_TSQL
- sysoledbusers
- sysoledbusers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysoledbusers system table
- sys.sysoledbusers compatibility view
ms.assetid: fe924c17-9cad-4b2b-8124-1e0fd82931e3
author: rothja
ms.author: jroth
ms.openlocfilehash: 932669feea7f267ae7120ec2c9e60eab07d23bad
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85893755"
---
# <a name="syssysoledbusers-transact-sql"></a>sys.sysoledbusers(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

    
> [!IMPORTANT]  
>  이 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] 시스템 테이블은 이전 버전과의 호환성을 위해서만 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에 뷰로 포함되어 있습니다. 대신 [카탈로그 뷰](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md) 를 사용 하는 것이 좋습니다.  
  
 지정되어 있는 연결된 서버에 대한 각 사용자 및 암호 매핑마다 한 행을 포함합니다. **sysoledbusers** 은 **master** 데이터베이스에 저장 됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**rmtsrvid**|**smallint**|서버의 SID(보안 ID 번호)입니다.|  
|**rmtloginame**|**nvarchar (** 128 **)**|연결 된 **rmtservid**에 대해 **loginsid** 가 매핑되는 원격 로그인의 이름입니다.|  
|**rmtpassword**|**nvarchar (** 128 **)**|NULL을 반환합니다.|  
|**loginsid**|**varbinary (** 85 **)**|매핑될 로컬 로그인의 SID입니다.|  
|**status**|**smallint**|1인 경우 매핑에 사용자의 자격 증명을 사용해야 합니다.|  
|**changedate**|**datetime**|매핑 정보가 마지막으로 변경된 날짜입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;카탈로그 뷰](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [호환성 뷰&#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
