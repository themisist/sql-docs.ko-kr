---
title: SQLInstallTranslator 매핑 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLInstallTranslator function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLInstallTranslator
ms.assetid: bcd9ba4f-7834-4bc4-876e-c7478998e524
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8ab5ebccaac7ccf6374971c1d21040ad15fb3e55
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300585"
---
# <a name="sqlinstalltranslator-mapping"></a>SQLInstallTranslator 매핑
*Odbc 2.x 응용 프로그램이* odbc *3.x 드라이버를* 통해 **Sqlinstalltranslator** 를 호출 하면 드라이버 관리자는 호출을 **SQLInstallTranslatorEx**에 매핑합니다. 응용 프로그램은 *lpszInfFile* 인수가 NULL이 아닌 값으로 설정 *된 ODBC 3.x* 드라이버 관리자에서 **sqlinstalltranslator** 를 호출 하면 안 됩니다. ODBC입니다. ODBC 2.x에서 사용 되는 INF 파일은 이전 버전과의 *호환성을 위해서도 odbc 3.x*에서 더 이상 지원 *되지 않습니다.*
