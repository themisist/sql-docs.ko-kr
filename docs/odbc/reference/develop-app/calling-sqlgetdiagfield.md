---
title: SQLGetDiagField 호출 Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- application upgrades [ODBC], SQLGetDiagField
- backward compatibility [ODBC], SqlGetDiagField
- upgrading applications [ODBC], SQLGetDiagField
- SQLGetDiagField function [ODBC], calling
- compatibility [ODBC], SQLGetDiagField
ms.assetid: 3c4fb606-b81c-4f11-9820-f0a54e3bc401
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a097cbdd74cfcd76d2b102bb71dfccb974906709
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306264"
---
# <a name="calling-sqlgetdiagfield"></a>SQLGetDiagField 호출
*Odbc 2.x 응용 프로그램이* odbc 2.x 드라이버에서 **SQLGetDiagField** 를 호출 하면 *DiagIdentifier* 인수가 SQL_DIAG_CLASS_ORIGIN, SQL_DIAG_CLASS_SUBCLASS_ORIGIN, SQL_DIAG_CONNECTION_NAME, SQL_DIAG_MESSAGE_TEXT, SQL_DIAG_NATIVE, SQL_DIAG_NUMBER, SQL_DIAG_RETURNCODE, SQL_DIAG_SERVER_NAME 또는 SQL_DIAG_SQLSTATE 인 경우 드라이버는 * \*DiagInfoPtr* 에 SQL_SUCCESS와 적절 한 정보를 반환 *합니다.* 다른 모든 진단 필드는 SQL_ERROR을 반환 합니다.
