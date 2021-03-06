---
title: SQLSetConnectOption (Visual FoxPro ODBC 드라이버) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLSetConnectOption function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 5a35449e-4694-4ee5-9fa1-45d5a8fe7823
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2af208663f1e91250faad0ca9538b76bcec43b06
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81301504"
---
# <a name="sqlsetconnectoption-visual-foxpro-odbc-driver"></a>SQLSetConnectOption(Visual FoxPro ODBC 드라이버)
> [!NOTE]  
>  이 항목에는 Visual FoxPro ODBC 드라이버 관련 정보가 포함 되어 있습니다. 이 함수에 대 한 일반 정보는 [ODBC API 참조](../../odbc/reference/syntax/odbc-api-reference.md)에서 적절 한 항목을 참조 하세요.  
  
 지원: 부분  
  
 ODBC API 규칙: 수준 1  
  
 연결의 여러 측면을 제어 하는 옵션을 설정 합니다. 이 함수는 부분적으로 지원 됩니다. 드라이버는 *foption* 인수에 대 한 모든 값을 지원 하지만 SQL_TXN_ISOLATION *foption* 인수에 대 한 *vparam* 값 중 일부를 지원 하지 않습니다.  
  
 다음 표에서는 **SQLSetConnectOption**의 VISUAL FoxPro ODBC 드라이버 구현과 관련 된 동작만 포함 하는 인수만 설명 합니다.  
  
|*fOption*|설명|  
|---------------|-------------|  
|SQL_AUTOCOMMIT|SQL_AUTOCOMMIT_OFF를 선택 하는 경우 응용 프로그램에서 [Sqltransact](../../odbc/microsoft/sqltransact-visual-foxpro-odbc-driver.md)을 사용 하 여 트랜잭션을 명시적으로 커밋하거나 롤백해야 합니다. Visual FoxPro ODBC 드라이버는 완료 시 불가능 문을 자동으로 커밋하지 않습니다. 문이 불가능 경우 드라이버가 트랜잭션을 시작 합니다.|  
|SQL_CURRENT_QUALIFIER|은 (는) 0 개 이상의 [자유 테이블이](../../odbc/microsoft/visual-foxpro-terminology.md)포함 된 디렉터리의 정규화 된 경로 또는 정규화 된 [데이터베이스](../../odbc/microsoft/visual-foxpro-terminology.md) 이름일 수 있습니다.|  
|SQL_LOGINTIMEOUT|"드라이버를 사용할 수 없음" 오류를 반환 합니다.|  
|SQL_CURSORS|"드라이버를 사용할 수 없음" 오류를 반환 합니다.|  
|SQL_PACKET_SIZE|"드라이버를 사용할 수 없음" 오류를 반환 합니다.|  
|SQL_TXN_ISOLATION|드라이버는 SQL_TXN_READ_COMMITTED만 허용 합니다.<br /><br /> 다음 *Vparam*은 지원 되지 않습니다.<br /><br /> SQL_TXN_READ_UNCOMMITTED<br /><br /> SQL_TXN_REAPEATABLE_READ<br /><br /> SQL_TXN_SERIALIZABLE|  
  
 자세한 내용은 *ODBC 프로그래머 참조*에서 [SQLSetConnectOption](../../odbc/reference/syntax/sqlsetconnectoption-function.md) 를 참조 하세요.
