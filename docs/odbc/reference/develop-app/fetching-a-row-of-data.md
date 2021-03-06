---
title: 데이터 행 페치 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLFetch function [ODBC], fetching a row of data
- cursors [ODBC], fetching rows
- result sets [ODBC], fetching
- fetches [ODBC], row of data
ms.assetid: 16d4a380-0d83-456b-aeee-f10738944e86
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a702f561b756d5305020df9f015d3ea4b444caa6
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81305674"
---
# <a name="fetching-a-row-of-data"></a>데이터 행 페치
데이터 행을 페치 하기 위해 응용 프로그램은 **Sqlfetch**를 호출 합니다. **Sqlfetch** 는 모든 종류의 커서를 사용 하 여 호출할 수 있지만 행 집합 커서를 앞 으로만 이동 전용 방향으로 이동 합니다. **Sqlfetch** 는 커서를 다음 행으로 이동 하 고 **SQLBindCol**에 대 한 호출을 사용 하 여 바인딩된 모든 열에 대 한 데이터를 반환 합니다. 커서가 결과 집합의 끝에 도달 하면 **Sqlfetch** 는 SQL_NO_DATA을 반환 합니다. **Sqlfetch**호출에 대 한 예제는 [SQLBindCol 사용](../../../odbc/reference/develop-app/using-sqlbindcol.md)을 참조 하세요.  
  
 **Sqlfetch** 를 구현 하는 방법은 드라이버 마다 다르지만 일반적인 패턴은 드라이버에서 데이터 원본에서 바인딩된 열의 데이터를 검색 하 고, 바인딩된 변수의 형식에 따라 변환 하 고, 변환 된 데이터를 이러한 변수에 추가 하는 것입니다. 드라이버가 데이터를 변환할 수 없는 경우 **Sqlfetch** 는 오류를 반환 합니다. 응용 프로그램은 계속 해 서 행을 인출할 수 있지만 현재 행에 대 한 데이터가 손실 됩니다. 바인딩되지 않은 열에 대 한 데이터는 드라이버에 따라 달라 지지만 대부분의 드라이버는이를 검색 하 여 삭제 하거나 전혀 검색 하지 않습니다.  
  
 또한 드라이버는 바인딩된 모든 길이/표시기 버퍼의 값을 설정 합니다. 열에 대 한 데이터 값이 NULL 인 경우 드라이버는 해당 길이/표시기 버퍼를 SQL_NULL_DATA으로 설정 합니다. 데이터 값이 NULL이 아닌 경우 드라이버는 변환 후 길이/표시기 버퍼를 데이터의 바이트 길이로 설정 합니다. 두 개 이상의 함수 호출로 검색 되는 긴 데이터를 사용 하는 경우를 제외 하 고이 길이를 확인할 수 없는 경우 드라이버는 길이/표시기 버퍼를 SQL_NO_TOTAL 설정 합니다. 정수 및 날짜 구조와 같은 고정 길이 데이터 형식의 경우 바이트 길이는 데이터 형식의 크기입니다.  
  
 문자 및 이진 데이터와 같은 가변 길이 데이터의 경우 드라이버는 열에 바인딩된 버퍼의 바이트 길이에 대해 변환 된 데이터의 바이트 길이를 확인 합니다. 버퍼의 길이는 **SQLBindCol**의 *bufferlength* 인수에 지정 됩니다. 변환 된 데이터의 바이트 길이가 버퍼의 바이트 길이 보다 큰 경우 드라이버는 버퍼에 맞게 데이터를 자르고, 길이/표시기 버퍼에 잘린 길이를 반환 하 고, SQL_SUCCESS_WITH_INFO을 반환 하 고, 진단에 SQLSTATE 01004 (데이터 잘림)을 배치 합니다. 이에 대 한 유일한 예외는 SQLSTATE 22001 (문자열 데이터, 오른쪽 잘림)을 반환 하는 **Sqlfetch**에서 반환 될 때 가변 길이 책갈피를 잘라내는 경우입니다.  
  
 고정 길이 데이터는 바인딩된 버퍼의 크기가 데이터 형식의 크기인 것으로 가정 하므로 잘리지 않습니다. 응용 프로그램은 일반적으로 전체 데이터 값을 저장할 만큼 충분히 많은 버퍼를 바인딩되기 때문에 데이터 잘림는 드물게 발생 합니다. 메타 데이터에서 필요한 크기를 결정 합니다. 그러나 응용 프로그램은 너무 작을 것으로 알고 있는 버퍼를 명시적으로 바인딩할 수 있습니다. 예를 들어 파트 설명의 처음 20 개 문자 또는 긴 텍스트 열의 처음 100 문자를 검색 하 여 표시할 수 있습니다.  
  
 문자 데이터는 잘린 경우에도 응용 프로그램에 반환 되기 전에 드라이버가 null로 종료 되어야 합니다. Null 종료 문자는 반환 된 바이트 길이에 포함 되지 않지만 바인딩된 버퍼에는 공간이 필요 합니다. 예를 들어 응용 프로그램에서 ASCII 문자 집합에 문자 데이터로 구성 된 문자열을 사용 하 고, 드라이버에서 반환할 데이터의 50 문자를 사용 하며, 응용 프로그램의 버퍼 길이는 25 바이트 라고 가정 합니다. 응용 프로그램의 버퍼에서 드라이버는 처음 24 자 다음에 null 종료 문자를 반환 합니다. 길이/표시기 버퍼에서 바이트 길이 50을 반환 합니다.  
  
 응용 프로그램은 결과 집합을 만드는 문을 실행 하기 전에 SQL_ATTR_MAX_ROWS 문 특성을 설정 하 여 결과 집합의 행 수를 제한할 수 있습니다. 예를 들어 보고서 서식을 지정 하는 데 사용 되는 응용 프로그램의 미리 보기 모드에는 보고서의 첫 페이지를 표시 하는 데 충분 한 데이터만 필요 합니다. 결과 집합의 크기를 제한 하 여 이러한 기능이 더 빠르게 실행 될 수 있습니다. 이 statement 특성은 네트워크 트래픽을 줄이기 위한 것 이며 모든 드라이버에서 지원 되지 않을 수 있습니다.
