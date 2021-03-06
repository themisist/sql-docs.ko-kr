---
title: 연결 옵션 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connection options [ODBC]
- ODBC driver for Oracle [ODBC], connection options
- custom connection options [ODBC]
ms.assetid: abfdc133-cb33-435f-a467-fbe15444f687
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 25cfe2a897b0c312f91cd0c1e41ad6fa11725ab8
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81281313"
---
# <a name="connect-options"></a>연결 옵션
> [!IMPORTANT]  
>  이 기능은 이후 버전의 Windows에서 제거 될 예정입니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 애플리케이션은 수정하세요. 대신 Oracle에서 제공 하는 ODBC 드라이버를 사용 합니다.  
  
 이러한 옵션을 사용 하면 응용 프로그램 내에서 데이터베이스 연결을 사용자 지정할 수 있습니다.  
  
|연결 옵션|참고|  
|--------------------|-----------|  
|SQL_AUTOCOMMIT|SQL_AUTOCOMMIT_OFF를 선택 하는 경우 응용 프로그램은 [Sqltransact](../../odbc/microsoft/core-level-api-functions-odbc-driver-for-oracle.md)을 사용 하 여 트랜잭션을 명시적으로 커밋하거나 롤백해야 합니다.|  
|SQL_ODBC_CURSORS|이 연결 특성은 드라이버 관리자에서 구현 됩니다.|  
|SQL_OPT_TRACE|이 연결 특성은 드라이버 관리자에서 구현 됩니다.|  
|SQL_OPT_TRACEFILE|이 연결 특성은 드라이버 관리자에서 구현 됩니다.|  
|SQL_TRANSLATE_DLL|"드라이버를 사용할 수 없음" 오류를 반환 합니다.|  
|SQL_TRANSLATE_OPTION|변환 .dll에 전달 된 32 비트 값입니다.|  
|SQL_TXN_ISOLATION|드라이버는 SQL_TXN_READ_COMMITTED만 허용 합니다.<br /><br /> 다음 vParams는 지원 되지 않습니다.<br /><br /> SQL_TXN_READ_UNCOMMITTED<br /><br /> SQL_TXN_REAPEATABLE_READ<br /><br /> SQL_TXN_SERIALIZABLE|  
|SQL_ATTR_ENLIST_IN_DTC|이 ODBC 3.0 연결 특성을 사용 하면 Microsoft 구성 요소 서비스 (또는 Windows NT를 사용 하는 경우 MTS)에서 조정 된 분산 트랜잭션에서 Oracle 용 ODBC 드라이버를 사용할 수 있습니다. 이 메서드는 *pITransaction* 에 *vparam* 인수로 트랜잭션에 대 한 인터페이스 포인터를 제공 합니다.|  
|SQL_ATTR_CONNECTION_DEAD|이 읽기 전용 ODBC 3.5 연결 특성을 사용 하면 Oracle 서버에 대 한 연결이 실패 했는지 여부를 확인할 수 있습니다. 가져오기 전용; 를 설정할 수 없습니다.|
