---
title: SQLExecute 함수 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLExecute
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLExecute
helpviewer_keywords:
- SQLExecute function [ODBC]
ms.assetid: 9286a01d-cde2-4b90-af94-9fd7f8da48bf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5306567aebc229a8bc9d1d3c91bcbd8e79391752
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81286073"
---
# <a name="sqlexecute-function"></a>SQLExecute 함수
**규칙**  
 소개 된 버전: ODBC 1.0 표준 준수: ISO 92  
  
 **요약**  
 **Sqlexecute** 는 문에 매개 변수 표식이 있는 경우 매개 변수 표식 변수의 현재 값을 사용 하 여 준비 된 문을 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
  
SQLRETURN SQLExecute(  
     SQLHSTMT     StatementHandle);  
```  
  
## <a name="arguments"></a>인수  
 *StatementHandle*  
 입력 문 핸들입니다.  
  
## <a name="returns"></a>반환  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_NEED_DATA, SQL_STILL_EXECUTING, SQL_ERROR, SQL_NO_DATA, SQL_INVALID_HANDLE 또는 SQL_PARAM_DATA_AVAILABLE입니다.  
  
## <a name="diagnostics"></a>진단  
 **Sqlexecute** 에서 SQL_ERROR 또는 SQL_SUCCESS_WITH_INFO를 반환 하는 경우 *HandleType* SQL_HANDLE_STMT의 및 *StatementHandle* *핸들* 을 사용 하 여 **SQLGetDiagRec** 를 호출 하 여 연결 된 SQLSTATE 값을 얻을 수 있습니다. 다음 표에서는 **Sqlexecute** 에서 일반적으로 반환 하는 SQLSTATE 값을 나열 하 고이 함수의 컨텍스트에서 각 항목에 대해 설명 합니다. "(DM)" 표기법은 드라이버 관리자에서 반환 된 SQLSTATEs의 설명 보다 앞에 나옵니다. 다른 설명이 없는 한 각 SQLSTATE 값과 연결 된 반환 코드는 SQL_ERROR 됩니다.  
  
|SQLSTATE|Error|Description|  
|--------------|-----------|-----------------|  
|01000|일반 경고|드라이버 관련 정보 메시지입니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01001|커서 작업 충돌|*StatementHandle* 와 연결 된 준비 된 문에는 위치 지정 update 또는 delete 문이 포함 되어 있고 행 또는 행을 두 개 이상 업데이트 하거나 삭제 하지 않았습니다. 하나 이상의 행에 대 한 업데이트에 대 한 자세한 내용은 **SQLSetStmtAttr**의 SQL_ATTR_SIMULATE_CURSOR *특성* 에 대 한 설명을 참조 하십시오.<br /><br /> 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01003|Set 함수에서 NULL 값이 제거 되었습니다.|*StatementHandle* 와 연결 된 준비 된 문에는 set 함수 (예: **AVG**, **MAX**, **MIN**등)가 포함 되어 있지만 **COUNT** set 함수는 포함 되지 않으며 NULL 인수 값은 함수를 적용 하기 전에 제거 되었습니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01004|문자열 데이터, 오른쪽이 잘렸습니다.|출력 매개 변수에 대해 반환 된 문자열 또는 이진 데이터 때문에 비어 있지 않은 문자 또는 NULL이 아닌 이진 데이터가 잘렸습니다. 문자열 값인 경우 오른쪽이 잘렸습니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01006|권한 해지 안 됨|*StatementHandle* 와 연결 된 준비 된 문이 **REVOKE** 문이 고 사용자에 게 지정 된 권한이 없습니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01007|권한이 부여 되지 않음|*StatementHandle* 와 연결 된 준비 된 문이 **GRANT** 문이 고 사용자에 게 지정 된 권한을 부여할 수 없습니다.|  
|01 S 02|옵션 값 변경 됨|구현 작업 조건 때문에 지정 된 문 특성이 잘못 되었습니다. 따라서 유사한 값이 일시적으로 대체 되었습니다. (**SQLGetStmtAttr** 를 호출 하 여 임시로 대체 된 값을 확인할 수 있습니다.) 대체 값은 커서가 닫힐 때까지 *StatementHandle* 에 유효 합니다 .이 시점에서 statement 특성은 이전 값으로 되돌아갑니다. 변경할 수 있는 문 특성은 SQL_ATTR_CONCURRENCY, SQL_ATTR_CURSOR_TYPE, SQL_ATTR_KEYSET_SIZE, SQL_ATTR_MAX_LENGTH, SQL_ATTR_MAX_ROWS, SQL_ATTR_QUERY_TIMEOUT, SQL_ATTR_SIMULATE_CURSOR입니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|01S07|소수 잘림|입력/출력 또는 출력 매개 변수에 대해 반환 된 데이터가 잘렸습니다 .이는 숫자 데이터 형식의 소수 부분이 잘렸거나 시간, 타임 스탬프 또는 interval 데이터 형식에 대 한 시간 구성 요소의 소수 부분이 잘린 것입니다.<br /><br /> 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|07002|COUNT 필드가 잘못 되었습니다.|**SQLBindParameter** 에 지정 된 매개 변수 개수가 \* *StatementText*에 포함 된 SQL 문의 매개 변수 개수 보다 낮습니다.<br /><br /> **SQLBindParameter** 가 null 포인터로 *설정 되지* 않은 *StrLen_or_IndPtr* SQL_NULL_DATA 또는 SQL_DATA_AT_EXEC으로 설정 되지 않고 *inputoutputtype* 이 SQL_PARAM_OUTPUT로 설정 되지 않은 상태에서 **SQLBindParameter** 에 지정 된 매개 변수 개수가 **StatementText*에 포함 된 SQL 문의 매개 변수 개수 보다 큰지 여부를 호출 했습니다.|  
|07006|제한 된 데이터 형식 특성 위반|바인딩된 매개 변수에 대 한 **SQLBindParameter** 의 *ValueType* 인수에 의해 식별 되는 데이터 값을 **SQLBindParameter**의 *ParameterType* 인수로 식별 된 데이터 형식으로 변환할 수 없습니다.<br /><br /> SQL_PARAM_INPUT_OUTPUT 또는 SQL_PARAM_OUTPUT로 바인딩된 매개 변수에 대해 반환 된 데이터 값을 **SQLBindParameter**의 *ValueType* 인수로 식별 된 데이터 형식으로 변환할 수 없습니다.<br /><br /> 하나 이상의 행에 대 한 데이터 값을 변환할 수 없지만 하나 이상의 행이 성공적으로 반환 된 경우이 함수는 SQL_SUCCESS_WITH_INFO을 반환 합니다.|  
|07007|제한 된 매개 변수 값 위반|매개 변수 형식 SQL_PARAM_INPUT_OUTPUT_STREAM는 파트에서 데이터를 보내고 받는 매개 변수에만 사용 됩니다. 이 매개 변수 형식에는 입력 바인딩된 버퍼를 사용할 수 없습니다.<br /><br /> 이 오류는 매개 변수 형식이 SQL_PARAM_INPUT_OUTPUT 되 고 \* **SQLBindParameter** 에 지정 된 *StrLen_or_IndPtr* SQL_NULL_DATA, SQL_DEFAULT_PARAM, SQL_LEN_DATA_AT_EXEC (LEN) 또는 SQL_DATA_AT_EXEC와 같지 않은 경우에 발생 합니다.|  
|07S01|기본 매개 변수 사용이 잘못 되었습니다.|**SQLBindParameter**로 설정 된 매개 변수 값이 SQL_DEFAULT_PARAM 되었으며 해당 매개 변수는 ODBC 정식 프로시저 호출에 대 한 매개 변수가 아닙니다.|  
|08S01|통신 연결 오류|드라이버가 연결 된 드라이버와 데이터 원본 간의 통신 연결이 함수 처리를 완료 하기 전에 실패 했습니다.|  
|21S02|파생 테이블의 수준이 열 목록과 일치 하지 않습니다.|*StatementHandle* 와 연결 된 준비 된 문에는 **CREATE VIEW** 문이 포함 되 고, 정규화 되지 않은 열 목록 (sql 문의 *열 식별자* 인수에서 뷰에 대해 지정 된 열 수)에는 sql 문의 *쿼리 사양* 인수에서 정의한 파생 테이블의 열 수보다 많은 이름이 포함 되어 있습니다.|  
|22001|문자열 데이터, 오른쪽 잘림|열에 문자 또는 이진 값을 할당 하 여 비어 있지 않은 (문자) 또는 null이 아닌 (이진) 문자 또는 바이트가 잘렸습니다.|  
|22002|표시기 변수가 필요한 데 제공 되지 않았습니다.|NULL 데이터가 **SQLBindParameter** 에 의해 설정 된 *StrLen_or_IndPtr* null 포인터인 출력 매개 변수에 바인딩되어 있습니다.|  
|22003|숫자 값이 범위를 벗어났습니다.|*StatementHandle* 와 연결 된 준비 된 문에 바인딩된 숫자 매개 변수가 포함 되어 있고 매개 변수 값으로 인해 연결 된 테이블 열에 할당 될 때 잘린 숫자의 전체 부분이 소수 부분을 벗어났습니다.<br /><br /> 하나 이상의 입력/출력 또는 출력 매개 변수에 대해 숫자 값 (숫자 또는 문자열)을 반환 하면 잘린 숫자의 전체 부분이 소수 부분으로 표시 되지 않습니다.|  
|22007|날짜/시간 형식이 잘못 되었습니다.|*StatementHandle* 와 연결 된 준비 된 문에는 날짜, 시간 또는 타임 스탬프 구조를 바인딩된 매개 변수로 포함 하 고 매개 변수는 각각 잘못 된 날짜, 시간 또는 타임 스탬프를 포함 하는 SQL 문이 포함 되어 있습니다.<br /><br /> Input/output 또는 output 매개 변수는 날짜, 시간 또는 타임 스탬프 C 구조에 바인딩되고 반환 된 매개 변수의 값은 각각 잘못 된 날짜, 시간 또는 타임 스탬프입니다. 함수는 SQL_SUCCESS_WITH_INFO를 반환 합니다.|  
|22008|Datetime 필드 오버플로|*StatementHandle* 와 연결 된 준비 된 문에는 계산 시 잘못 된 날짜, 시간 또는 타임 스탬프 구조가 생성 된 datetime 식이 포함 된 SQL 문이 포함 되어 있습니다.<br /><br /> 입/출력 또는 출력 매개 변수에 대해 계산 된 datetime 식이 잘못 된 날짜, 시간 또는 타임 스탬프 C 구조를 가져왔습니다.|  
|22012|0으로 나누었습니다.|*StatementHandle* 와 연결 된 준비 문에 0으로 나누기를 발생 시킨 산술 식이 포함 되어 있습니다.<br /><br /> 입/출력 또는 출력 매개 변수에 대해 계산 된 산술 식의 결과로 0으로 나누었습니다.|  
|22015|간격 필드 오버플로입니다.|StatementText에는 interval SQL 데이터 형식으로 변환 될 때 유효 자릿수가 손실 되는 정확한 숫자 또는 간격 매개 변수가 포함 되어 있습니다. * \**<br /><br /> StatementText에는 열에서 숫자 데이터 형식으로 변환 될 때 숫자 데이터 형식에 표시 되지 않는 필드를 두 개 이상 포함 하는 interval 매개 변수가 포함 되어 있습니다. * \**<br /><br /> StatementText에 interval sql 형식에 할당 된 매개 변수 데이터가 포함 되어 있으며 interval sql 형식에 C 형식의 값이 표시 되지 않았습니다. * \**<br /><br /> 정확한 숫자 또는 간격 SQL 형식의 입력/출력 또는 출력 매개 변수를 interval C 유형에 할당 하면 유효 자릿수가 손실 됩니다.<br /><br /> Input/output 또는 output 매개 변수가 interval C 구조에 할당 된 경우 interval 데이터 구조에 데이터가 표시 되지 않습니다.|  
|22018|캐스트 사양에 대 한 문자 값이 잘못 되었습니다.|StatementText에는 정확히 또는 근사 숫자, datetime 또는 interval 데이터 형식인 C 형식이 포함 되어 있습니다. * \** 열의 SQL 형식이 문자 데이터 형식입니다. 열에 있는 값이 바인딩된 C 형식의 올바른 리터럴이 아닙니다.<br /><br /> 입/출력 또는 출력 매개 변수가 반환 된 경우 SQL 유형은 정확한 수치 또는 근사치, datetime 또는 interval 데이터 형식입니다. C 형식이 SQL_C_CHAR 되었습니다. 열 값이 바인딩된 SQL 형식의 올바른 리터럴이 아닙니다.|  
|22019|잘못 된 이스케이프 문자|*StatementHandle* 와 연결 된 준비 된 문에 **WHERE** 절에 **이스케이프** 를 사용 하는 **LIKE** 조건자가 포함 되어 **있으며 이스케이프 문자 다음의** 길이가 1과 같지 않습니다.|  
|22025|이스케이프 시퀀스가 잘못 되었습니다.|**WHERE** 절에 *StatementHandle* 와 연결 된 준비 된 문 (**예** : _패턴 값_ **이스케이프** _이스케이프 문자_)이 포함 되어 있고 패턴 값의 이스케이프 문자 다음에 오는 문자가 "%" 또는 "_" 중 하나가 아닙니다.|  
|23000|무결성 제약 조건 위반|*StatementHandle* 와 연결 된 준비 된 문에 매개 변수가 포함 되어 있습니다. 연결 된 테이블 열에서 NOT NULL로 정의 된 열에 대 한 매개 변수 값이 NULL입니다. 고유 값만 포함 하도록 제한 된 열에 중복 값이 제공 되었거나 일부 다른 무결성 제약 조건을 위반 했습니다.|  
|24000|잘못된 커서 상태|*StatementHandle* **Sqlfetch** 또는 **sqlfetchscroll**에 의해 커서가 배치 되었습니다. 이 오류는 **sqlfetch** 또는 **sqlfetchscroll** 이 SQL_NO_DATA 반환 되지 않은 경우 드라이버 관리자에 의해 반환 되 고, **Sqlfetch** 또는 **sqlfetchscroll** 에서 SQL_NO_DATA를 반환한 경우 드라이버에서 반환 됩니다.<br /><br /> 커서가 *StatementHandle*에서 열려 있습니다.<br /><br /> *StatementHandle* 와 연결 된 준비 된 문에는 위치 지정 update 또는 delete statemen, t가 포함 되 고, 커서는 결과 집합의 시작 앞 이나 결과 집합의 끝에 배치 되었습니다.|  
|40001|Serialization 오류|다른 트랜잭션과의 리소스 교착 상태 때문에 트랜잭션이 롤백 되었습니다.|  
|40003|문 완료를 알 수 없음|이 함수를 실행 하는 동안 연결 된 연결에 실패 하 여 트랜잭션의 상태를 확인할 수 없습니다.|  
|42000|구문 오류 또는 액세스 위반|사용자에 게 *StatementHandle*와 연결 된 준비 된 문을 실행할 수 있는 권한이 없습니다.|  
|44000|WITH CHECK OPTION 위반|*StatementHandle* 와 연결 된 준비 된 문에는 표시 된 테이블에 대해 수행 된 **Insert** 문 또는 **with CHECK OPTION**을 지정 하 여 만든 표시 된 테이블에서 파생 된 테이블이 포함 되어 있습니다. 이러한 **insert 문의 영향** 을 받는 하나 이상의 행이 더 이상 표시 되지 않습니다.<br /><br /> *StatementHandle* 와 연결 된 준비 된 문에는 표시 된 테이블에 대해 수행 된 **Update** 문 또는 **with CHECK OPTION**을 지정 하 여 만든 표시 된 테이블에서 파생 된 테이블이 포함 되어 있습니다. 그러면 **update** 문의 영향을 받는 하나 이상의 행이 표시 된 테이블에 더 이상 표시 되지 않습니다.|  
|HY000|일반 오류|특정 SQLSTATE가 없고 구현 별 SQLSTATE가 정의 되지 않은 오류가 발생 했습니다. MessageText 버퍼에서 **SQLGetDiagRec** 에 의해 반환 되는 오류 메시지는 오류 및 해당 원인을 설명 합니다. * \**|  
|HY001|메모리 할당 오류|드라이버에서 함수 실행 또는 완료를 지 원하는 데 필요한 메모리를 할당할 수 없습니다.|  
|HY008|작업 취소됨|*StatementHandle*에 대해 비동기 처리를 사용 하도록 설정 했습니다. 함수가 호출 되었으며 실행이 완료 되기 전에 **sqlcancel** 또는 **Sqlcancelhandle** 이 *StatementHandle*에 대해 호출 되었습니다. 그런 다음 *StatementHandle*에서 함수를 다시 호출 했습니다.<br /><br /> 함수가 호출 되 고 실행이 완료 되기 전에 **sqlcancel** 또는 **sqlcancelhandle** 이 다중 스레드 응용 프로그램의 다른 스레드에서 *StatementHandle* 호출 되었습니다.|  
|HY010|함수 시퀀스 오류|(DM) *StatementHandle*연결 된 연결 핸들에 대해 비동기적으로 실행 되는 함수가 호출 되었습니다. 이 비동기 함수는 **Sqlexecute** 함수가 호출 될 때 실행 되 고 있습니다.<br /><br /> (DM) **Sqlexecute**, **sqlexecdirect**또는 **SQLMoreResults** 가 *StatementHandle* 에 대해 호출 되 고 SQL_PARAM_DATA_AVAILABLE 반환 되었습니다. 이 함수는 모든 스트리밍된 매개 변수에 대 한 데이터를 검색 하기 전에 호출 되었습니다.<br /><br /> (DM) *StatementHandle* 에 대해 비동기적으로 실행 되는 함수 (이 함수 아님)가 호출 되었으며이 함수가 호출 될 때 계속 실행 중입니다.<br /><br /> (DM) **Sqlexecute**, **sqlexecdirect**, **SQLBulkOperations**또는 **SQLSetPos** 가 *StatementHandle* 에 대해 호출 되 고 SQL_NEED_DATA 반환 되었습니다. 이 함수는 모든 실행 시 데이터 매개 변수 또는 열에 대해 데이터를 보내기 전에 호출 되었습니다.<br /><br /> (DM) *StatementHandle* 가 준비 되지 않았습니다.|  
|HY013|메모리 관리 오류|메모리 부족 상태로 인해 기본 메모리 개체에 액세스할 수 없기 때문에 함수 호출을 처리할 수 없습니다.|  
|HY090|잘못 된 문자열 또는 버퍼 길이입니다.|**SQLBindParameter**를 사용 하 여 설정 된 매개 변수 값이 null 포인터이 고 매개 변수 길이 값이 0, SQL_NULL_DATA SQL_DATA_AT_EXEC, SQL_DEFAULT_PARAM 또는 SQL_LEN_DATA_AT_EXEC_OFFSET 보다 작거나 같은 경우<br /><br /> **SQLBindParameter**로 설정 된 매개 변수 값이 null 포인터가 아닙니다. C 데이터 형식이 SQL_C_BINARY 되었거나 SQL_C_CHAR. 매개 변수 길이 값이 0 보다 작지만 SQL_NTS, SQL_NULL_DATA, SQL_DEFAULT_PARAM 또는 SQL_DATA_AT_EXEC 아니거나 SQL_LEN_DATA_AT_EXEC_OFFSET 보다 작거나 같은 경우<br /><br /> **SQLBindParameter** 에 의해 바인딩된 매개 변수 길이 값이 SQL_DATA_AT_EXEC로 설정 되었습니다. SQL 형식이 SQL_LONGVARCHAR, SQL_LONGVARBINARY 또는 long 데이터 원본에 해당 하는 데이터 형식입니다. **SQLGetInfo** 의 SQL_NEED_LONG_DATA_LEN 정보 형식은 "Y" 였습니다.|  
|HY105|매개 변수 형식이 잘못 되었습니다.|**SQLBindParameter** 의 인수 *inputoutputtype* 에 지정 된 값이 SQL_PARAM_OUTPUT 되었고 매개 변수가 입력 매개 변수입니다.|  
|HY109|커서 위치가 잘못 되었습니다.|준비 된 문이 배치 된 update 또는 delete 문 이며 삭제 되었거나 인출할 수 없는 행에 대해 **SQLSetPos** 또는 **sqlfetchscroll**에 의해 커서가 배치 되었습니다.|  
|HY117|알 수 없는 트랜잭션 상태로 인해 연결이 일시 중단 되었습니다. 연결 끊기 및 읽기 전용 함수만 허용 됩니다.|(DM) 일시 중단 된 상태에 대 한 자세한 내용은 [Sqlendtran 함수](../../../odbc/reference/syntax/sqlendtran-function.md)를 참조 하세요.|  
|HYC00|선택적 기능이 구현 되지 않음|SQL_ATTR_CONCURRENCY 및 SQL_ATTR_CURSOR_TYPE statement 특성의 현재 설정 조합이 드라이버 또는 데이터 원본에서 지원 되지 않습니다.<br /><br /> SQL_ATTR_USE_BOOKMARKS statement 특성이 SQL_UB_VARIABLE로 설정 되 고 SQL_ATTR_CURSOR_TYPE statement 특성이 해당 드라이버가 책갈피를 지원 하지 않는 커서 유형으로 설정 되었습니다.|  
|HYT00|제한 시간이 만료되었습니다.|데이터 원본에서 결과 집합을 반환 하기 전에 쿼리 제한 시간이 만료 되었습니다. 제한 시간은 **SQLSetStmtAttr**, SQL_ATTR_QUERY_TIMEOUT을 통해 설정 됩니다.|  
|HYT01|연결 제한 시간이 만료 되었습니다.|데이터 원본이 요청에 응답 하기 전에 연결 제한 시간이 만료 되었습니다. 연결 제한 시간은 **SQLSetConnectAttr**, SQL_ATTR_CONNECTION_TIMEOUT을 통해 설정 됩니다.|  
|IM001|드라이버가이 기능을 지원 하지 않습니다.|(DM) *StatementHandle* 연결 된 드라이버는 함수를 지원 하지 않습니다.|  
|IM017|비동기 알림 모드에서는 폴링을 사용할 수 없습니다.|알림 모델을 사용할 때마다 폴링은 사용 하지 않도록 설정 됩니다.|  
|IM018|이 핸들에서 이전 비동기 작업을 완료 하기 위해 **SQLCompleteAsync** 가 호출 되지 않았습니다.|핸들에 대 한 이전 함수 호출이 SQL_STILL_EXECUTING을 반환 하 고 알림 모드가 설정 된 경우에는 핸들에 대해 **SQLCompleteAsync** 를 호출 하 여 사후 처리를 수행 하 고 작업을 완료 해야 합니다.|  
  
 **Sqlexecute** 는 데이터 원본이 문과 연결 된 SQL 문을 평가 하는 시점에 따라 **sqlexecute**에서 반환 될 수 있는 모든 SQLSTATE를 반환할 수 있습니다.  
  
## <a name="comments"></a>주석  
 **Sqlexecute** 는 **sqlexecute**에서 준비 된 문을 실행 합니다. 응용 프로그램이 **sqlexecute**호출에서 결과를 처리 하거나 삭제 한 후에는 새 매개 변수 값을 사용 하 여 **sqlexecute** 를 다시 호출할 수 있습니다. 준비 된 실행에 대 한 자세한 내용은 [준비 된 실행](../../../odbc/reference/develop-app/prepared-execution-odbc.md)을 참조 하세요.  
  
 **Select** 문을 두 번 이상 실행 하려면 응용 프로그램은 **select** 문을 다시 실행 하기 전에 **SQLCloseCursor** 를 호출 해야 합니다.  
  
 데이터 원본이 수동 커밋 모드에 있고 (명시적 트랜잭션 시작 필요) 트랜잭션이 아직 시작 되지 않은 경우 드라이버는 SQL 문을 보내기 전에 트랜잭션을 시작 합니다. 자세한 내용은 [트랜잭션](../../../odbc/reference/develop-app/transactions-odbc.md)을 참조하세요.  
  
 응용 프로그램에서 **Sqlprepare** 를 사용 하 여 **COMMIT** 또는 **ROLLBACK** 문을 **제출할 때이** 를 준비 하는 경우 DBMS 제품 간에 상호 운용할 수 없습니다. 트랜잭션을 커밋하거나 롤백하려면 **Sqlendtran**을 호출 합니다.  
  
 **Sqlexecute** 가 실행 시 데이터 매개 변수를 발견 하면 SQL_NEED_DATA를 반환 합니다. 응용 프로그램은 **Sqlparamdata** 및 **sqlparamdata**를 사용 하 여 데이터를 보냅니다. [SQLBindParameter](../../../odbc/reference/syntax/sqlbindparameter-function.md), [sqlparamdata](../../../odbc/reference/syntax/sqlparamdata-function.md), [Sqlparamdata](../../../odbc/reference/syntax/sqlputdata-function.md)및 [Long 데이터 전송](../../../odbc/reference/develop-app/sending-long-data.md)을 참조 하세요.  
  
 **Sqlexecute** 에서 데이터 원본의 행에 영향을 주지 않는 검색 된 update, insert 또는 delete 문을 실행 하는 경우 **sqlexecute** 에 대 한 호출은 SQL_NO_DATA을 반환 합니다.  
  
 SQL_ATTR_PARAMSET_SIZE statement 특성 값이 1 보다 크고 sql 문에 매개 변수 표식이 하나 이상 포함 되어 있는 경우 **sqlexecute** 는 **SQLBindParameter**에 대 한 호출의 * \*parametervalueptr* 인수가 가리키는 배열의 각 매개 변수 값 집합에 대해 sql 문을 한 번씩 실행 합니다. 자세한 내용은 [매개 변수 값 배열](../../../odbc/reference/develop-app/arrays-of-parameter-values.md)을 참조 하세요.  
  
 책갈피를 사용 하도록 설정 하 고 책갈피를 지원할 수 없는 쿼리가 실행 되는 경우 드라이버는 특성 값을 변경 하 고 SQLSTATE 01 S 02 (옵션 값이 변경 됨)을 반환 하 여 책갈피를 지 원하는 환경으로 강제 변환 하려고 합니다. 특성을 변경할 수 없는 경우 드라이버는 SQLSTATE HY024 (잘못 된 특성 값)을 반환 해야 합니다.  
  
> [!NOTE]  
>  연결 풀링을 사용 하는 경우 응용 프로그램은 데이터베이스 또는 데이터베이스의 컨텍스트를 변경 하는 SQL 문을 실행 하지 않아야 합니다. 예를 들어 데이터 원본에서 사용 되는 카탈로그를 변경 하는 SQL Server의 **USE** _database_ 문과 같이 데이터베이스를 변경 해야 합니다.  
  
## <a name="code-example"></a>코드 예  
 [SQLBindParameter](../../../odbc/reference/syntax/sqlbindparameter-function.md), [SQLBulkOperations](../../../odbc/reference/syntax/sqlbulkoperations-function.md), [sqlputdata](../../../odbc/reference/syntax/sqlputdata-function.md)및 [SQLSetPos](../../../odbc/reference/syntax/sqlsetpos-function.md)를 참조 하세요.  
  
## <a name="related-functions"></a>관련 함수  
  
|원하는 정보|참조 항목|  
|---------------------------|---------|  
|결과 집합의 열에 버퍼 바인딩|[SQLBindCol 함수](../../../odbc/reference/syntax/sqlbindcol-function.md)|  
|문 처리 취소|[SQLCancel 함수](../../../odbc/reference/syntax/sqlcancel-function.md)|  
|커서 닫기|[SQLCloseCursor 함수](../../../odbc/reference/syntax/sqlclosecursor-function.md)|  
|커밋 또는 롤백 작업 실행|[SQLEndTran 함수(SQLEndTran Function)](../../../odbc/reference/syntax/sqlendtran-function.md)|  
|SQL 문 실행|[SQLExecDirect 함수](../../../odbc/reference/syntax/sqlexecdirect-function.md)|  
|여러 행의 데이터 페치|[SQLFetch 함수](../../../odbc/reference/syntax/sqlfetch-function.md)|  
|데이터 블록 가져오기 또는 결과 집합을 통한 스크롤|[SQLFetchScroll 함수](../../../odbc/reference/syntax/sqlfetchscroll-function.md)|  
|문 핸들 해제|[SQLFreeStmt 함수](../../../odbc/reference/syntax/sqlfreestmt-function.md)|  
|커서 이름 반환|[SQLGetCursorName 함수](../../../odbc/reference/syntax/sqlgetcursorname-function.md)|  
|데이터 열의 일부 또는 전체를 가져오는 중|[SQLGetData 함수(SQLGetData Function)](../../../odbc/reference/syntax/sqlgetdata-function.md)|  
|다음 매개 변수를 반환 하 여 데이터 보내기|[SQLParamData 함수](../../../odbc/reference/syntax/sqlparamdata-function.md)|  
|실행을 위한 문 준비|[SQLPrepare 함수](../../../odbc/reference/syntax/sqlprepare-function.md)|  
|실행 시 매개 변수 데이터 보내기|[SQLPutData 함수](../../../odbc/reference/syntax/sqlputdata-function.md)|  
|커서 이름 설정|[SQLSetCursorName 함수](../../../odbc/reference/syntax/sqlsetcursorname-function.md)|  
|문 특성 설정|[SQLSetStmtAttr 함수](../../../odbc/reference/syntax/sqlsetstmtattr-function.md)|  
  
## <a name="see-also"></a>참고 항목  
 [ODBC API 참조](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [ODBC 헤더 파일](../../../odbc/reference/install/odbc-header-files.md)
