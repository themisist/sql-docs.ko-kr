---
title: sys. asymmetric_keys (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- asymmetric_keys
- sys.asymmetric_keys_TSQL
- asymmetric_keys_TSQL
- sys.asymmetric_keys
dev_langs:
- TSQL
helpviewer_keywords:
- sys.asymmetric_keys catalog view
ms.assetid: bbca796a-9bb5-4a62-9ca8-1d255984553d
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: fdd5636a3b3cf700dccc855e26bb64f85f0c1207
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85652363"
---
# <a name="sysasymmetric_keys-transact-sql"></a>sys.asymmetric_keys(Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  각 비대칭 키에 대해 행을 반환합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|키 이름입니다. 데이터베이스 내에서 고유합니다.|  
|**principal_id**|**int**|이 키를 소유하는 데이터베이스 보안 주체의 ID입니다.|  
|**asymmetric_key_id**|**int**|키 ID입니다. 데이터베이스 내에서 고유합니다.|  
|**pvt_key_encryption_type**|**char(2)**|키가 암호화된 방법입니다.<br /><br /> NA = 암호화되지 않음<br /><br /> MK = 마스터 키로 암호화됨<br /><br /> PW = 사용자 정의 암호로 암호화됨<br /><br /> SK = 서비스 마스터 키로 암호화됨|  
|**pvt_key_encryption_type_desc**|**nvarchar(60)**|프라이빗 키를 암호화하는 방법에 대한 설명입니다.<br /><br /> NO_PRIVATE_KEY<br /><br /> ENCRYPTED_BY_MASTER_KEY<br /><br /> ENCRYPTED_BY_PASSWORD<br /><br /> ENCRYPTED_BY_SERVICE_MASTER_KEY|  
|**n**|**varbinary(32)**|키의 SHA-1 해시입니다. 해시는 전역적으로 고유합니다.|  
|**알고리즘과**|**char(2)**|키에 사용된 알고리즘입니다.<br /><br /> 1R = 512비트 RSA<br /><br /> 2R = 1024비트 RSA<br /><br /> 3R = 2048비트 RSA|  
|**algorithm_desc**|**nvarchar(60)**|키에 사용된 알고리즘에 대한 설명입니다.<br /><br /> RSA_512<br /><br /> RSA_1024<br /><br /> RSA_2048|  
|**key_length**|**int**|키의 비트 길이입니다.|  
|**sid**|**varbinary(85)**|이 키의 로그인 SID입니다. EKM(Extensible Key Management) 키의 경우 이 값은 NULL입니다.|  
|**string_sid**|**nvarchar(128)**|키의 로그인 SID를 나타내는 문자열입니다. EKM(Extensible Key Management) 키의 경우 이 값은 NULL입니다.|  
|**public_key**|**varbinary(max)**|공개 키입니다.|  
|**attested_by**|**nvarchar(260)**|시스템에서만 사용됩니다.|  
|**provider_type**|**nvarchar(120)**|암호화 공급자의 유형입니다.<br /><br /> CRYPTOGRAPHIC PROVIDER = EKM(확장 가능 키 관리) 키<br /><br /> NULL = EKM(확장 가능 키 관리) 키가 아닌 경우|  
|**cryptographic_provider_guid**|**uniqueidentifier**|암호화 공급자의 GUID입니다. Extensible Key Management가 아닌 키의 경우 이 값은 NULL입니다.|  
|**cryptographic_provider_algid**|**sql_variant**|암호화 공급자의 알고리즘 ID입니다. Extensible Key Management가 아닌 키의 경우 이 값은 NULL입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;보안 카탈로그 뷰](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [EKM&#41;&#40;확장 가능 키 관리](../../relational-databases/security/encryption/extensible-key-management-ekm.md)   
 [Transact-sql&#41;&#40;카탈로그 뷰](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-asymmetric-key-transact-sql.md)  
  
  
