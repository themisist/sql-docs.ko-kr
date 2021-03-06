---
title: sysmail_help_configure_sp (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_help_configure_sp
- sysmail_help_configure_sp_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_help_configure_sp
ms.assetid: e598d4c8-3041-4965-b046-dce3a8e3d3e0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 307b1a1259210890d0b21abdc7a26f0e321e49b3
ms.sourcegitcommit: d855def79af642233cbc3c5909bc7dfe04c4aa23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87122703"
---
# <a name="sysmail_help_configure_sp-transact-sql"></a>sysmail_help_configure_sp(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  데이터베이스 메일의 구성 설정을 표시합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sysmail_help_configure_sp  [ [ @parameter_name = ] 'parameter_name' ]  
```  
  
## <a name="arguments"></a>인수  
`[ @parameter_name = ] 'parameter_name'`검색할 구성 설정의 이름입니다. 이 값을 지정 하면 구성 설정의 값이 ** \@ parameter_value** OUTPUT 매개 변수에 반환 됩니다. ** \@ Parameter_name** 지정 하지 않으면이 저장 프로시저는 인스턴스의 모든 데이터베이스 메일 구성 설정을 포함 하는 결과 집합을 반환 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 ** \@ Parameter_name** 지정 하지 않으면는 다음 열이 포함 된 결과 집합을 반환 합니다.  
  
| 열 이름 | 데이터 형식 | Description |
| ----------- | --------- | ----------- |
|**paramname**|**nvarchar(256)**|구성 매개 변수의 이름입니다.|  
|**paramvalue**|**nvarchar(256)**|구성 매개 변수의 값입니다.|  
|**description**|**nvarchar(256)**|구성 매개 변수에 대한 설명입니다.|  
  
## <a name="remarks"></a>설명  
 저장 프로시저 **sysmail_help_configure_sp** 인스턴스에 대 한 현재 데이터베이스 메일 구성 설정을 나열 합니다.  
  
 ** \@ Parameter_name** 지정 되었지만 ** \@ parameter_value**에 대해 출력 매개 변수가 제공 되지 않은 경우이 저장 프로시저는 출력을 생성 하지 않습니다.  
  
 **Sysmail_help_configure_sp** 저장 프로시저는 **msdb** 데이터베이스에 있으며 **dbo** 스키마가 소유 합니다. 현재 데이터베이스가 **msdb**가 아닌 경우 세 부분으로 된 이름을 사용 하 여 프로시저를 호출 해야 합니다.  
  
## <a name="permissions"></a>사용 권한  
 이 프로시저에 대 한 실행 권한은 기본적으로 **sysadmin** 고정 서버 역할의 멤버로 사용 됩니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에 대한 데이터베이스 메일 구성 설정 목록을 보여 줍니다.  
  
```  
EXECUTE msdb.dbo.sysmail_help_configure_sp ;  
```  
  
 다음은 줄 길이에 맞추어 편집된 결과 집합 예입니다.  
  
```  
paramname                       paramvalue      description  
------------------------------- --------------- -----------------------------------------------------------------------------  
AccountRetryAttempts            1               Number of retry attempts for a mail server  
AccountRetryDelay               5000            Delay between each retry attempt to mail server  
DatabaseMailExeMinimumLifeTime  600             Minimum process lifetime in seconds  
DefaultAttachmentEncoding       MIME            Default attachment encoding  
LoggingLevel                    2               Database Mail logging level: normal - 1, extended - 2 (default), verbose - 3  
MaxFileSize                     1000000         Default maximum file size  
ProhibitedExtensions            exe,dll,vbs,js  Extensions not allowed in outgoing mails  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터베이스 메일](../../relational-databases/database-mail/database-mail.md)   
 [Transact-sql&#41;&#40;저장 프로시저 데이터베이스 메일](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
