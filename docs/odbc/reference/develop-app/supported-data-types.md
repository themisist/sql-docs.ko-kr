---
title: 지원 되는 데이터 형식 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data types [ODBC], DBMS support
- interoperability [ODBC], data types
ms.assetid: a89d4bab-ef3c-45c2-aa72-2639b3e0f856
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d19cde2d531819a60229dd7a780181571e169503
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81307784"
---
# <a name="supported-data-types"></a>지원되는 데이터 형식
Dbms에서 지 원하는 데이터 형식은 매우 다양 합니다. 응용 프로그램은 **SQLGetTypeInfo**를 호출 하 여 지원 되는 데이터 형식의 이름과 특성을 결정할 수 있습니다. 데이터 형식 이름의 넓은 변동 때문에 응용 프로그램은 **CREATE TABLE** 문에서 **SQLGetTypeInfo** 에 의해 반환 되는 데이터 형식 이름을 사용 해야 합니다. 자세한 내용은 [ODBC의 데이터 형식](../../../odbc/reference/develop-app/data-types-in-odbc.md)을 참조 하세요.
