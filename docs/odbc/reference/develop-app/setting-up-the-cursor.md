---
title: 커서 설정 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- scrollable cursors [ODBC]
- cursors [ODBC], scrollable
- cursors [ODBC], creating
ms.assetid: b80afb0e-ef2f-408f-86f5-a392edd99a56
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 805d8076c853513d86f9a3a92d9342d1224226c9
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81299803"
---
# <a name="setting-up-the-cursor"></a>커서 설정
응용 프로그램은 결과 집합을 만드는 문을 실행 하기 전에 커서 유형을 지정할 수 있습니다. SQL_ATTR_CURSOR_TYPE statement 특성을 사용 하 여이를 수행 합니다. 응용 프로그램에서 명시적으로 형식을 지정 하지 않은 경우에는 앞 으로만 이동 가능한 커서가 사용 됩니다. 혼합 커서를 가져오기 위해 응용 프로그램은 키 집합 커서를 지정 하지만 결과 집합 크기 보다 작은 키 집합 크기를 선언 합니다.  
  
 키 집합 커서와 혼합 커서의 경우 응용 프로그램에서 키 집합 크기를 지정할 수도 있습니다. SQL_ATTR_KEYSET_SIZE statement 특성을 사용 하 여이를 수행 합니다. 키 집합 크기가 기본값인 0으로 설정 된 경우 키 집합 크기는 결과 집합 크기로 설정 되 고 키 집합 커서는 사용 됩니다. 커서를 연 후 키 집합 크기를 변경할 수 있습니다.  
  
 응용 프로그램은 행 집합 크기를 설정할 수도 있습니다. 자세한 내용은이 섹션의 앞부분에 나오는 [블록 커서 사용](../../../odbc/reference/develop-app/using-block-cursors.md)을 참조 하세요.
