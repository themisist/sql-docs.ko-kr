---
title: sys.sys주석 (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.syscomments_TSQL
- syscomments
- syscomments_TSQL
- sys.syscomments
dev_langs:
- TSQL
helpviewer_keywords:
- sys.syscomments compatibility view
- syscomments system table
ms.assetid: 767dd410-6bc9-4c4a-ab0f-6d2cf6163426
author: rothja
ms.author: jroth
ms.openlocfilehash: 49473b85d6c0a52f9c7ec7ed4bab519b19b04693
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85883482"
---
# <a name="syssyscomments-transact-sql"></a>sys.syscomments(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  데이터베이스 내의 각 뷰,  규칙,  기본값,  트리거,  CHECK  제약 조건,  DEFAULT  제약 조건 및 저장 프로시저에 대한 항목을 포함합니다. **텍스트** 열에는 원래 SQL 정의 문이 포함 됩니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 대신 sys.sql_modules를 사용하는 것이 좋습니다. 자세한 내용은 [sql_modules &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md)을 참조 하십시오.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|해당 텍스트를 적용할 개체 ID입니다.|  
|**number**|**smallint**|그룹화된 경우에 프로시저 그룹 내의 번호입니다.<br /><br /> 0  =  항목이 프로시저가 아닙니다.|  
|**colid**|**smallint**|4,000자보다 긴 개체 정의의 행 시퀀스 번호입니다.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**ctext**|**varbinary(8000)**|SQL  정의 문의 원시 바이트입니다.|  
|**texttype**|**smallint**|0  =  사용자 제공 설명<br /><br /> 1  =  시스템 제공 설명<br /><br /> 4  =  암호화된 설명|  
|**language**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**됨**|**bit**|프로시저 정의가 난독 처리되었는지 여부를 나타냅니다.<br /><br /> 0  =  난독 처리되지 않음<br /><br /> 1  =  난독 처리됨<br /><br /> 중요 저장 프로시저 정의를 난독 처리 하려면 CREATE procedure를 ENCRYPTION 키워드와 함께 사용 합니다. ** \* \* \* \* **|  
|**압축**|**bit**|항상 0을 반환합니다. 이것은 프로시저가 압축되었음을 의미합니다.|  
|**text**|**nvarchar(4000)**|SQL  정의 문의 실제 텍스트입니다.<br /><br /> 디코딩된 식의 의미 체계는 원본 텍스트와 동일하지만 구문은 일치하지 않을 수 있습니다. 예를 들어 공백은 디코딩된 식에서 제거됩니다.<br /><br /> 이 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] 호환 뷰는 현재 구조에서 정보 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 를 가져오며 **nvarchar (4000)** 정의 보다 많은 문자를 반환할 수 있습니다. **sp_help** 는 **nvarchar (4000)** 를 텍스트 열의 데이터 형식으로 반환 합니다. **Sys.syscomments** 작업 시 **nvarchar (max)** 를 사용 하는 것이 좋습니다. 새 개발 작업의 경우 **sys.syscomments**를 사용 하지 마세요.|  
  
## <a name="see-also"></a>참고 항목  
 [시스템 테이블을 시스템 뷰로 매핑 &#40;Transact-sql&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [호환성 뷰&#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
