---
title: sys. crypt_properties (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- crypt_properties
- crypt_properties_TSQL
- sys.crypt_properties_TSQL
- sys.crypt_properties
dev_langs:
- TSQL
helpviewer_keywords:
- sys.crypt_properties catalog view
ms.assetid: d5684f5a-30b1-418e-ae4d-ab040db9257e
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5a4c03687f6adac3f67f3e6aa231c384a6d5e009
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85725797"
---
# <a name="syscrypt_properties-transact-sql"></a>sys.crypt_properties(Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  보안 개체와 연결된 각 암호화 속성에 대해 행을 반환합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**class**|**tinyint**|속성이 존재하는 항목의 클래스를 식별합니다.<br /><br /> 1 = 개체 또는 열<br /> 5 = 어셈블리|  
|**class_desc**|**nvarchar(60)**|속성이 존재하는 항목의 클래스에 대한 설명입니다.<br /><br /> OBJECT_OR_COLUMN<br /> ASSEMBLY|  
|**major_id**|**int**|속성이 존재하는 항목의 ID입니다. 이 ID는 해당 클래스에 따라 해석됩니다.|  
|**n**|**varbinary(32)**|사용된 인증서 또는 비대칭 키의 SHA-1 해시입니다.|  
|**crypt_type**|**char (4)**|암호화 유형입니다.<br /><br /> SPVC = 인증서 개인 키로 서명 됨<br /><br /> SPVA = 비대칭 개인 키로 서명 됨<br /><br /> CPVC = 인증서 프라이빗 키를 사용한 카운터 서명<br /><br /> CPVA = 비대칭 키를 사용한 카운터 서명|  
|**crypt_type_desc**|**nvarchar(60)**|암호화 유형에 대한 설명입니다.<br /><br /> SIGNATURE BY CERTIFICATE<br /><br /> SIGNATURE BY ASYMMETRIC KEY<br /><br /> COUNTER SIGNATURE BY CERTIFICATE<br /><br /> COUNTER SIGNATURE BY ASYMMETRIC KEY|  
|**crypt_property**|**varbinary(max)**|부호 있는 비트 또는 암호화된 비트입니다. 서명 된 모듈의 경우 모듈의 서명 비트입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;보안 카탈로그 뷰](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [보안 개체](../../relational-databases/security/securables.md)   
 [CREATE CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [Transact-sql&#41;&#40;대칭 키 만들기](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [Transact-sql&#41;&#40;비대칭 키 만들기](../../t-sql/statements/create-asymmetric-key-transact-sql.md)   
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
