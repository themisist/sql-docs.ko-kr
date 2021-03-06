---
title: 프로그래밍 지침(ODBC Driver)
description: macOS 및 Linux 기반 Microsoft ODBC Driver for SQL Server의 프로그래밍 기능은 SQL Server Native Client의 ODBC(ODBC)를 기반으로 합니다.
ms.custom: ''
ms.date: 05/06/2020
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
author: v-makouz
ms.author: v-daenge
ms.openlocfilehash: 8843bf303f20a7d8aa0baac5be3d9da4e7c54e01
ms.sourcegitcommit: fb1430aedbb91b55b92f07934e9b9bdfbbd2b0c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82886370"
---
# <a name="programming-guidelines"></a>프로그래밍 지침

[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

macOS 및 Linux 기반 [!INCLUDE[msCoName](../../../includes/msconame_md.md)] ODBC Driver for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]의 프로그래밍 기능은 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client([SQL Server Native Client(ODBC)](../../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md))를 기반으로 합니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client는 Windows Data Access Components의 ODBC를 기반으로 합니다([ODBC 프로그래머 참조](../../../odbc/reference/odbc-programmer-s-reference.md)).  

ODBC 애플리케이션은 unixODBC 헤더(`sql.h`, `sqlext.h`, `sqltypes.h` 및 `sqlucode.h`)를 포함한 후 `/usr/local/include/msodbcsql.h`를 포함하여 MARS(Multiple Active Result Set) 및 다른 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 고유 기능을 사용할 수 있습니다. 그런 다음, Windows ODBC 애플리케이션에서 사용하는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 관련 항목에 대해 동일한 기호화된 이름을 사용합니다.

## <a name="available-features"></a>사용 가능한 기능  
ODBC([SQL Server Native Client(ODBC)](../../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md))에 대한 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 설명서의 다음 섹션은 macOS 및 Linux 기반 ODBC 드라이버를 사용할 때 유용합니다.  

-   [SQL Server와 통신(ODBC)](../../../relational-databases/native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
-   [연결 및 쿼리 시간 제한 지원](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
-   [커서](../../../relational-databases/native-client-odbc-cursors/using-cursors-odbc.md)  
-   [날짜/시간 기능 향상(ODBC)](../../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
-   [쿼리 실행(ODBC)](../../../relational-databases/native-client-odbc-queries/executing-queries-odbc.md)  
-   [오류 및 메시지 처리](../../../relational-databases/native-client-odbc-error-messages/handling-errors-and-messages.md)  
-   [Kerberos 인증](../../../relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections.md)  
-   [큰 CLR 사용자 정의 형식(ODBC)](../../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md)  
-   [트랜잭션 수행(ODBC)(분산 트랜잭션 제외)](../../../relational-databases/native-client/odbc/performing-transactions-in-odbc.md)  
-   [결과 처리(ODBC)](../../../relational-databases/native-client-odbc-results/processing-results-odbc.md)  
-   [저장 프로시저 실행](../../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)
-   [스파스 열 지원(ODBC)](../../../relational-databases/native-client/odbc/sparse-columns-support-odbc.md)
-   [유효성 검사 없이 암호화 사용](../../../relational-databases/native-client/features/using-encryption-without-validation.md)
-   [테이블 반환 매개 변수](../../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)
-   [명령 및 데이터 API용 UTF-8 및 UTF-16](../../../relational-databases/native-client/features/utf-16-support-in-sql-server-native-client-11-0.md)
-   [카탈로그 함수 사용](../../../relational-databases/native-client/odbc/using-catalog-functions.md)  

## <a name="unsupported-features"></a>지원되지 않는 기능

다음 기능은 이 macOS 및 Linux 기반 ODBC 드라이버 릴리스에서 올바르게 작동하는 것으로 확인되지 않았습니다.

-   장애 조치(failover) 클러스터 연결
-   [투명한 네트워크 IP 확인](../using-transparent-network-ip-resolution.md)(ODBC 드라이버 17 이전)
-   [고급 드라이버 추적](/archive/blogs/mattn/enabling-advanced-driver-tracing-for-the-sql-native-client-odbc-drivers)

다음 기능은 이 macOS 및 Linux 기반 ODBC 드라이버 릴리스에서 사용할 수 없습니다. 

-   분산 트랜잭션(SQL_ATTR_ENLIST_IN_DTC 특성이 지원되지 않음)  
-   데이터베이스 미러링  
-   FILESTREAM  
-   [SQLSetConnectAttr](../../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md)에 설명된 ODBC 드라이버 성능 프로파일링 및 성능과 관련된 연결 특성은 다음과 같습니다.  
    -   SQL_COPT_SS_PERF_DATA  
    -   SQL_COPT_SS_PERF_DATA_LOG  
    -   SQL_COPT_SS_PERF_DATA_LOG_NOW  
    -   SQL_COPT_SS_PERF_QUERY  
    -   SQL_COPT_SS_PERF_QUERY_INTERVAL  
    -   SQL_COPT_SS_PERF_QUERY_LOG  
-   SQLBrowseConnect(17.2 이전 버전)
-   SQL_C_INTERVAL_YEAR_TO_MONTH와 같은 C 간격 유형([데이터 형식 식별자 및 설명자](../../../odbc/reference/appendixes/data-type-identifiers-and-descriptors.md)에 설명됨)
-   SQLSetConnectAttr 함수의 SQL_ATTR_ODBC_CURSORS 특성에 대한 SQL_CUR_USE_ODBC 값입니다.

## <a name="character-set-support"></a>문자 집합 지원

ODBC 드라이버 13 및 13.1의 경우 SQLCHAR 데이터는 UTF-8이어야 합니다. 다른 인코딩은 지원되지 않습니다.

ODBC 드라이버 17의 경우 다음 문자 세트/인코딩 중 하나의 SQLCHAR 데이터가 지원됩니다.

> [!NOTE]  
> `musl`과 `glibc`의 `iconv` 차이로 인해 이러한 로캘 대부분은 Alpine Linux에서 지원되지 않습니다.
>
> 자세한 내용은 [glibc의 기능 차이점](https://wiki.musl-libc.org/functional-differences-from-glibc.html)을 참조하세요.

|속성|Description|
|-|-|
|UTF-8|Unicode|
|CP437|MS-DOS 라틴어 미국|
|CP850|MS-DOS 라틴어 1|
|CP874|라틴어/태국어|
|CP932|일본어, Shift_JIS|
|CP936|중국어 간체, GBK|
|CP949|한국어, EUC-KR|
|CP950|중국어 번체, Big5|
|CP1251|키릴 자모|
|CP1253|그리스어|
|CP1256|아랍어|
|CP1257|발트어|
|CP1258|베트남어|
|ISO-8859-1 / CP1252|라틴어-1|
|ISO-8859-2 / CP1250|라틴어-2|
|ISO-8859-3|라틴어-3|
|ISO-8859-4|라틴어-4|
|ISO-8859-5|라틴어/키릴 자모|
|ISO-8859-6|라틴어/아랍어|
|ISO-8859-7|라틴어/그리스어|
|ISO-8859-8 / CP1255|히브리어|
|ISO-8859-9 / CP1254|터키어|
|ISO-8859-13|라틴어-7|
|ISO-8859-15|라틴어-9|

연결 시 드라이버에서 로드된 프로세스의 현재 로캘을 검색합니다. 위의 인코딩 중 하나를 사용하는 경우 드라이버에서 SQLCHAR(반각 문자) 데이터에 해당 인코딩을 사용하며, 그렇지 않으면 기본적으로 UTF-8을 사용합니다. 모든 프로세스는 기본적으로 “C” 로캘로 시작하므로(그리고 따라서 드라이버에서 기본적으로 UTF-8을 사용하므로), 애플리케이션이 위의 인코딩 중 하나를 사용해야 하는 경우 연결하기 전에 원하는 로캘을 명시적으로 지정하거나 빈 문자열(예: `setlocale(LC_ALL, "")`)을 사용해 환경의 로캘 설정을 사용함으로써 **setlocale** 함수를 사용하여 로캘을 적합하게 설정해야 합니다.

그러므로 인코딩이 UTF-8인 일반적인 Linux 또는 macOS 환경에서 ODBC 드라이버 13 또는 13.1에서 17로 업그레이드하는 사용자의 경우 해당 차이점이 발생하지 않습니다. 그러나 `setlocale()`을 통해 위 목록의 UTF-8이 아닌 인코딩을 사용하는 애플리케이션은 드라이버에 대한 데이터에 UTF-8 대신 해당 인코딩을 사용해야 합니다.

SQLWCHAR 데이터는 UTF-16LE(Little Endian)이어야 합니다.

SQLBindParameter를 사용하여 입력 매개 변수를 바인딩하는 경우 SQL_VARCHAR와 같은 반각 문자 SQL 형식을 지정하면 드라이버에서 제공된 데이터를 클라이언트 인코딩에서 기본(일반적으로 코드 페이지 1252) [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인코딩으로 변환합니다. 출력 매개 변수의 경우 드라이버에서 데이터와 연결된 정렬 정보에 지정된 인코딩에서 클라이언트 인코딩으로 변환합니다. 그러나 데이터 손실이 발생할 수 있습니다. --- 즉, 대상 인코딩에서 표현할 수 없는 원본 인코딩의 문자가 물음표('?')로 변환될 수 있습니다.

입력 매개 변수를 바인딩할 때 이 데이터 손실을 방지하려면 유니코드 SQL 문자 형식(예: SQL_NVARCHAR)을 지정합니다. 이 경우 드라이버는 클라이언트 인코딩에서 모든 유니코드 문자를 표현할 수 있는 UTF-16으로 변환합니다. 또한 서버의 대상 열 또는 매개 변수도 유니코드 형식(**nchar**, **nvarchar**, **ntext**) 또는 원래 원본 데이터의 모든 문자를 표현할 수 있는 정렬/인코딩을 포함하는 형식이어야 합니다. 출력 매개 변수에서 데이터 손실을 방지하려면 유니코드 SQL 형식 및 드라이버에서 데이터를 UTF-16으로 변환하게 하는 유니코드 C 형식(SQL_C_WCHAR) 또는 반각 C 형식을 지정하고 클라이언트 인코딩이 원본 데이터의 모든 문자를 표현할 수 있는지(UTF-8에서는 항상 가능) 확인합니다.

데이터 정렬 및 인코딩에 대한 자세한 내용은 [데이터 정렬 및 유니코드 지원](../../../relational-databases/collations/collation-and-unicode-support.md)을 참조하세요.

Windows와 Linux 및 macOS 기반 iconv 라이브러의 여러 버전 간에는 인코딩 변환에서 몇 가지 차이점이 있습니다. 코드 페이지 1255(히브리어)의 텍스트 데이터에는 유니코드로 변환하면 다르게 동작하는 하나의 코드 포인트(0xCA)가 있습니다. Windows의 경우 이 문자는 UTF-16 코드 포인트 0x05BA로 변환됩니다. 1\.15 이전 버전 libiconv를 포함하는 macOS 및 Linux의 경우 0x00CA로 변환됩니다. 2003 개정판 Big5/CP950(`BIG5-2003`)을 지원하지 않는 iconv 라이브러리를 포함하는 Linux의 경우 해당 개정판에서 추가된 문자는 올바르게 변환되지 않습니다. 코드 페이지 932(일본어, Shift-JIS)의 경우 원래 인코딩 표준에 정의되지 않은 문자를 해독한 결과도 다릅니다. 예를 들어 바이트 0x80은 Windows에서 U+0080으로 변환되지만 Linux 및 macOS에서는 iconv 버전에 따라 U+30FB가 될 수 있습니다.

ODBC 드라이버 13 및 13.1에서 UTF-8 멀티바이트 문자 또는 UTF-16 서로게이트가 SQLPutData 버퍼로 분할되면 데이터 손상이 발생합니다. 버퍼를 부분 문자 인코딩으로 끝나지 않는 SQLPutData 스트리밍에 사용합니다. 이 제한 사항은 ODBC 드라이버 17에서 제거되었습니다.

## <a name="openssl"></a><a name="bkmk-openssl"></a>OpenSSL
드라이버는 버전 17.4부터 OpenSSL을 동적으로 로드하므로 별도의 드라이버 파일 없이 버전 1.0 또는 1.1을 사용하는 시스템에서 실행할 수 있습니다. 여러 버전의 OpenSSL가 있는 경우에는 드라이버에서 최신 버전의 로드를 시도합니다. 드라이버는 현재 OpenSSL 1.0.x 및 1.1.x를 지원합니다.

> [!NOTE]  
> 드라이버나 그 구성 요소 중 하나를 사용하는 애플리케이션이 서로 다른 버전의 OpenSSL를 연결하거나 동적으로 로드하는 경우 잠재적 충돌 가능성이 있습니다. 여러 버전의 OpenSSL이 시스템에 있고 애플리케이션에서 이를 사용하는 경우, 오류로 인해 메모리가 손상되어 명확하거나 일관되게 표시되지 않을 수도 있으므로 애플리케이션과 드라이버에 의해 로드된 버전이 일치하지는 않는지 확인하는 것이 좋습니다.

## <a name="alpine-linux"></a><a name="bkmk-alpine"></a>Alpine Linux
이 문서를 작성한 시점을 기준으로 MUSL의 기본 스택 크기는 128K이어서 기본 ODBC 드라이버 기능에 충분하지만 애플리케이션이 무얼 하느냐에 따라 이 한도를 쉽게 초과할 수도 있으며, 특히 여러 스레드에서 드라이버를 호출하는 경우가 여기에 해당합니다. Alpine Linux상의 ODBC 애플리케이션이 `-Wl,-z,stack-size=<VALUE IN BYTES>`로 컴파일되어 스택 크기를 늘리는 것이 좋습니다. 참고로 대다수 GLIBC 시스템의 기본 스택 크기는 2MB입니다.

## <a name="additional-notes"></a>참고 사항  

1.  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인증 및 **호스트,포트**를 사용하여 DAC(관리자 전용 연결)를 만들 수 있습니다. Sysadmin 역할의 멤버는 먼저 DAC 포트를 검색해야 합니다. 방법에 대해 알아보려면 [데이터베이스 관리자용 진단 연결](../../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md#dac-port)을 참조하세요. 예를 들어 DAC 포트가 33000인 경우 다음과 같이 `sqlcmd`로 연결할 수 있습니다.  

    ```
    sqlcmd -U <user> -P <pwd> -S <host>,33000
    ```

    > [!NOTE]  
    > DAC 연결은 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인증을 사용해야 합니다.  
    
2.  UnixODBC 드라이버 관리자는 문 특성이 SQLSetConnectAttr을 통해 전달될 때 모든 문 특성에 대해 "잘못된 특성/옵션 식별자"를 반환합니다. Windows에서 SQLSetConnectAttr이 명령문 특성 값을 받을 때 드라이버가 연결 핸들의 자식인 모든 활성 명령문의 해당 값을 설정합니다.  

3.  다중 스레드 애플리케이션에서 드라이버를 사용하는 경우 unixODBC의 처리 유효성 검사가 성능 병목 상태가 될 수 있습니다. 이러한 시나리오에서는 `--enable-fastvalidate` 옵션으로 unixODBC를 컴파일링하여 성능을 크게 향상할 수 있습니다. 다만 이로 인해 잘못된 핸들을 ODBC API로 전달하는 애플리케이션의 경우 `SQL_INVALID_HANDLE` 오류 반환이 아닌 충돌이 발생할 수 있다는 데 유의해야 합니다.

## <a name="see-also"></a>참고 항목  
[질문과 대답](frequently-asked-questions-faq-for-odbc-linux.md)

[이 버전의 드라이버에서 알려진 문제](known-issues-in-this-version-of-the-driver.md)

[릴리스 정보](release-notes-odbc-sql-server-linux-mac.md)
