---
title: sys. sp_rda_get_rpo_duration (Transact-sql) | Microsoft Docs
description: Sp_rda_get_rpo_duration를 사용 하 여 원격 Azure 데이터베이스를 완전히 복원 하기 위해 준비 테이블에 유지 SQL Server는 마이그레이션된 데이터의 시간 수를 가져올 수 있습니다.
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: language-reference
f1_keywords:
- sys.sp_rda_get_rpo_duration
- sys.sp_rda_get_rpo_duration_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_get_rpo_duration stored procedure
ms.assetid: 35882067-3072-47ff-9024-ca453c0f49a7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e50e313e49b955b40497f28b2cb9265cf7717e3
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243358"
---
# <a name="syssp_rda_get_rpo_duration-transact-sql"></a>sys. sp_rda_get_rpo_duration (Transact-sql)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  지정 시간 복원이 필요한 경우 원격 Azure 데이터베이스를 전체 복원할 수 있도록 SQL Server 준비 테이블에 유지 되는 마이그레이션된 데이터의 시간을 가져옵니다. 
  
  자세한 내용은 [마이그레이션된 행을 일시적으로 유지 하 여 Azure 데이터에 대 한 데이터 손실의 위험을 줄이기 Stretch Database](../../sql-server/stretch-database/backup-stretch-enabled-databases-stretch-database.md#stretchRPO)를 참조 하세요.  
    
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)    
    
## <a name="syntax"></a>구문    
    
```    
    
sp_rda_get_rpo_duration @durationinhours output    
    
```    
    
## <a name="output-parameter"></a>출력 매개 변수    
 *\@durationinhours*    
  현재 스트레치 사용 데이터베이스에 대해 SQL Server 유지 하는 마이그레이션된 데이터의 시간 (null이 아닌 정수 값) 수입니다.    
    
## <a name="permissions"></a>사용 권한    
 Db_owner 권한이 필요 합니다.    
    
## <a name="remarks"></a>설명    
 [Sp_rda_set_rpo_duration &#40;transact-sql&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-rpo-duration-transact-sql.md)를 실행 하 여 값을 변경 합니다.    
    
## <a name="see-also"></a>참고 항목    
 [sp_rda_set_rpo_duration &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-rpo-duration-transact-sql.md)     
 [스트레치 사용 데이터베이스 복원 (Stretch Database)](../../sql-server/stretch-database/restore-stretch-enabled-databases-stretch-database.md)    
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)    
    
  
