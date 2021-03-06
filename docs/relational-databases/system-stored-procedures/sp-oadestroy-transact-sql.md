---
title: sp_OADestroy (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_OADestroy_TSQL
- sp_OADestroy
dev_langs:
- TSQL
helpviewer_keywords:
- sp_OADestroy
ms.assetid: 0bd1cff4-ceff-4095-9ae4-e1e65a80f5d6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 363d89a420d6fd927293fc39525e1a95d7ebd4b0
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85893427"
---
# <a name="sp_oadestroy-transact-sql"></a>sp_OADestroy(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  생성된 OLE 개체를 삭제합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_OADestroy objecttoken      
```  
  
## <a name="arguments"></a>인수  
 *objecttoken*  
 **Sp_OACreate**를 사용 하 여 이전에 만든 OLE 개체의 개체 토큰입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 0이 아닌 숫자(실패)이며 OLE Automation 개체가 반환한 HRESULT의 정수 값입니다.  
  
 HRESULT 반환 코드에 대 한 자세한 내용은 [OLE 자동화 반환 코드 및 오류 정보](../../relational-databases/stored-procedures/ole-automation-return-codes-and-error-information.md)를 참조 하세요.  
  
## <a name="remarks"></a>설명  
 **Sp_OADestroy** 를 호출 하지 않으면 만들어진 OLE 개체가 일괄 처리의 끝 부분에서 자동으로 삭제 됩니다.  
  
## <a name="permissions"></a>사용 권한  
 **Sysadmin** 고정 서버 역할의 멤버 자격 또는이 저장 프로시저에 대 한 execute 권한이 필요 합니다. `Ole Automation Procedures`OLE 자동화와 관련 된 시스템 프로시저를 사용 하려면 구성을 사용 하도록 **설정** 해야 합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 이전에 만든 **SQLServer** 개체를 삭제 합니다.  
  
```  
EXEC @hr = sp_OADestroy @object;  
IF @hr <> 0  
BEGIN  
   EXEC sp_OAGetErrorInfo @object  
    RETURN  
END;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;OLE 자동화 저장 프로시저](../../relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql.md)   
 [OLE 자동화 예제 스크립트](../../relational-databases/stored-procedures/ole-automation-sample-script.md)  
  
  
