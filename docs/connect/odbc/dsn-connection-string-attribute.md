---
title: ODBC DSN 연결 문자열 키워드
description: 이 페이지에는 연결 문자열과 DSN용 키워드, 그리고 SQL Server용 ODBC 드라이버에서 사용할 수 있는 SQLSetConnectAttr 및 SQLGetConnectAttr용 연결 특성을 나열합니다.
ms.custom: ''
ms.date: 02/04/2019
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
ms.reviewer: v-chojas
ms.author: v-jizho2
author: karinazhou
ms.openlocfilehash: bf0c3d880b9ebd13106be4247d42afd9d9316da9
ms.sourcegitcommit: 1a96abbf434dfdd467d0a9b722071a1ca1aafe52
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81528985"
---
# <a name="dsn-and-connection-string-keywords-and-attributes"></a>DSN 및 연결 문자열 키워드 및 특성

이 페이지에는 연결 문자열과 DSN용 키워드, 그리고 SQL Server용 ODBC 드라이버에서 사용할 수 있는 SQLSetConnectAttr 및 SQLGetConnectAttr용 연결 특성을 나열합니다.

## <a name="supported-dsnconnection-string-keywords-and-connection-attributes"></a>지원되는 DSN/연결 문자열 키워드 및 연결 특성

다음 표에는 각 플랫폼(L: Linux, M: Mac, W: Windows)에 Linux; M: macOS; W: 특성이 나열되어 있습니다. 자세한 내용을 보려면 키워드 또는 특성을 클릭하세요.

| DSN/연결 문자열 키워드 | 연결 특성 | 플랫폼 |
|-|-|-|
| [Addr](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [주소](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [AnsiNPW](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_ANSI_NPW](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssansinpw) | LMW |
| [APP](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [ApplicationIntent](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_APPLICATION_INTENT](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssapplicationintent) | LMW |
| [AttachDBFileName](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_ATTACHDBFILENAME](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssattachdbfilename) | LMW |
| [인증](../../connect/odbc/dsn-connection-string-attribute.md#authentication---sql_copt_ss_authentication) | [SQL_COPT_SS_AUTHENTICATION](../../connect/odbc/dsn-connection-string-attribute.md#authentication---sql_copt_ss_authentication) | LMW |
| [AutoTranslate](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_TRANSLATE](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptsstranslate) | LMW |
| [ColumnEncryption](../../connect/odbc/dsn-connection-string-attribute.md#columnencryption---sql_copt_ss_column_encryption) | [SQL_COPT_SS_COLUMN_ENCRYPTION](../../connect/odbc/dsn-connection-string-attribute.md#columnencryption---sql_copt_ss_column_encryption) | LMW |
| [ConnectRetryCount](../../connect/odbc/windows/connection-resiliency-in-the-windows-odbc-driver.md) | [SQL_COPT_SS_CONNECT_RETRY_COUNT](../../connect/odbc/windows/connection-resiliency-in-the-windows-odbc-driver.md) | W |
| [ConnectRetryInterval](../../connect/odbc/windows/connection-resiliency-in-the-windows-odbc-driver.md) | [SQL_COPT_SS_CONNECT_RETRY_INTERVAL](../../connect/odbc/windows/connection-resiliency-in-the-windows-odbc-driver.md) | W |
| [Database](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_ATTR_CURRENT_CATALOG](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| [설명](../../connect/odbc/dsn-connection-string-attribute.md#description) | | LMW |
| [드라이버](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [DSN](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [Encrypt](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_ENCRYPT](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssencrypt) | LMW |
| [Failover_Partner](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_FAILOVER_PARTNER](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssfailoverpartner) | W |
| [FailoverPartnerSPN](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_FAILOVER_PARTNER_SPN](../../relational-databases/native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md) | W |
| [FileDSN](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [KeepAlive](../../connect/odbc/linux-mac/connection-string-keywords-and-data-source-names-dsns.md)(v17.4+, DSN 전용)| | LMW |
| [KeepAliveInterval](../../connect/odbc/linux-mac/connection-string-keywords-and-data-source-names-dsns.md)(v17.4+, DSN 전용) | | LMW |
| [KeystoreAuthentication](../../connect/odbc/using-always-encrypted-with-the-odbc-driver.md#connection-string-keywords) | | LMW |
| [KeystorePrincipalId](../../connect/odbc/using-always-encrypted-with-the-odbc-driver.md#connection-string-keywords) | | LMW |
| [KeystoreSecret](../../connect/odbc/using-always-encrypted-with-the-odbc-driver.md#connection-string-keywords) | | LMW |
| [언어](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [MARS_Connection](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_MARS_ENABLED](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssmarsenabled) | LMW |
| [MultiSubnetFailover](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_MULTISUBNET_FAILOVER](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssmultisubnetfailover) | LMW |
| [Net](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [Network](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [PWD](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [QueryLog_On](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_PERF_QUERY](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfquery) | W |
| [QueryLogFile](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_PERF_QUERY_LOG](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfquerylog) | W |
| [QueryLogTIme](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_PERF_QUERY_INTERVAL](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfqueryinterval) | W |
| [QuotedId](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_QUOTED_IDENT](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssquotedident) | LMW |
| [Regional](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [SaveFile](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [Server](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [ServerSPN](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_SERVER_SPN](../../relational-databases/native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md) | LMW |
| [StatsLog_On](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_PERF_DATA](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfdata) | W |
| [StatsLogFile](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_PERF_DATA_LOG](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfdatalog) | W |
| [TransparentNetworkIPResolution](../../connect/odbc/dsn-connection-string-attribute.md#transparentnetworkipresolution---sql_copt_ss_tnir) | [SQL_COPT_SS_TNIR](../../connect/odbc/dsn-connection-string-attribute.md#transparentnetworkipresolution---sql_copt_ss_tnir) | LMW |
| [Trusted_Connection](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_INTEGRATED_SECURITY](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssintegratedsecurity) | LMW |
| [TrustServerCertificate](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | [SQL_COPT_SS_TRUST_SERVER_CERTIFICATE](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptsstrustservercertificate) | LMW |
| [UID](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| [UseFMTONLY](../../connect/odbc/dsn-connection-string-attribute.md#usefmtonly) | | LMW |
| [WSID](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md) | | LMW |
| | [SQL_ATTR_ACCESS_MODE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_ACCESS_MODE) | LMW |
| | [SQL_ATTR_ASYNC_DBC_EVENT](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | W |
| | [SQL_ATTR_ASYNC_DBC_FUNCTIONS_ENABLE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | W |
| | [SQL_ATTR_ASYNC_DBC_PCALLBACK](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | W |
| | [SQL_ATTR_ASYNC_DBC_PCONTEXT](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | W |
| | [SQL_ATTR_ASYNC_ENABLE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | W |
| | [SQL_ATTR_AUTO_IPD](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| | [SQL_ATTR_AUTOCOMMIT](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_AUTOCOMMIT) | LMW |
| | [SQL_ATTR_CONNECTION_DEAD](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| | [SQL_ATTR_CONNECTION_TIMEOUT](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| | [SQL_ATTR_DBC_INFO_TOKEN](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| | [SQL_ATTR_LOGIN_TIMEOUT](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_LOGIN_TIMEOUT) | LMW |
| | [SQL_ATTR_METADATA_ID](../../odbc/reference/syntax/sqlsetconnectattr-function.md) | LMW |
| | [SQL_ATTR_ODBC_CURSORS](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_ODBC_CURSORS) | LMW |
| | [SQL_ATTR_PACKET_SIZE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_PACKET_SIZE) | LMW |
| | [SQL_ATTR_QUIET_MODE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_QUIET_MODE) | LMW |
| | [SQL_ATTR_RESET_CONNECTION](../../odbc/reference/develop-driver/upgrading-a-3-5-driver-to-a-3-8-driver.md#connection-pooling) <br> (SQL_COPT_SS_RESET_CONNECTION) | LMW |  
| | [SQL_ATTR_TRACE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_OPT_TRACE) | LMW |
| | [SQL_ATTR_TRACEFILE](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_OPT_TRACEFILE) | LMW |
| | [SQL_ATTR_TRANSLATE_LIB](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_TRANSLATE_DLL) | LMW |
| | [SQL_ATTR_TRANSLATE_OPTION](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_TRANSLATE_OPTION) | LMW |
| | [SQL_ATTR_TXN_ISOLATION](../../odbc/reference/syntax/sqlsetconnectattr-function.md) <br> (SQL_TXN_ISOLATION) | LMW |
| | [SQL_COPT_SS_ACCESS_TOKEN](dsn-connection-string-attribute.md#sql_copt_ss_access_token) | LMW |
| | [SQL_COPT_SS_ANSI_OEM](dsn-connection-string-attribute.md#sql_copt_ss_ansi_oem)| W |
| | [SQL_COPT_SS_BCP](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssbcp) | LMW |
| | [SQL_COPT_SS_BROWSE_CACHE_DATA](../../relational-databases/native-client-odbc-api/sqlbrowseconnect.md) | LMW |
| | [SQL_COPT_SS_BROWSE_CONNECT](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssbrowseconnect) | LMW |
| | [SQL_COPT_SS_BROWSE_SERVER](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssbrowseserver) | LMW |
| | [SQL_COPT_SS_CEKEYSTOREDATA](dsn-connection-string-attribute.md#sql_copt_ss_cekeystoredata) | LMW |
| | [SQL_COPT_SS_CEKEYSTOREPROVIDER](dsn-connection-string-attribute.md#sql_copt_ss_cekeystoreprovider) | LMW |
| | [SQL_COPT_SS_CLIENT_CONNECTION_ID](../../relational-databases/native-client-odbc-api/sqlgetconnectattr.md) | LMW |
| | [SQL_COPT_SS_CONCAT_NULL](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssconcatnull) | LMW |
| | [SQL_COPT_SS_CONNECTION_DEAD](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssconnectiondead) | LMW |
| | [SQL_COPT_SS_ENLIST_IN_DTC](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssenlistindtc) | W |
| | [SQL_COPT_SS_ENLIST_IN_XA](dsn-connection-string-attribute.md#sql_copt_ss_enlist_in_xa) | LMW |
| | [SQL_COPT_SS_FALLBACK_CONNECT](dsn-connection-string-attribute.md#sql_copt_ss_fallback_connect) | LMW |
| | [SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD](../../relational-databases/native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md) | LMW |
| | [SQL_COPT_SS_MUTUALLY_AUTHENTICATED](../../relational-databases/native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md) | LMW |
| | [SQL_COPT_SS_OLDPWD](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssoldpwd) | LMW |
| | [SQL_COPT_SS_PERF_DATA_LOG_NOW](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssperfdatalognow) | W |
| | [SQL_COPT_SS_PRESERVE_CURSORS](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptsspreservecursors) | LMW |
| | [SQL_COPT_SS_SPID](../../connect/odbc/dsn-connection-string-attribute.md#sql_copt_ss_spid)(v17.5+) | LMW |
| | [SQL_COPT_SS_TXN_ISOLATION](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptsstxnisolation) | LMW |
| | [SQL_COPT_SS_USER_DATA](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptssuserdata) | LMW |
| | [SQL_COPT_SS_WARN_ON_CP_ERROR](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md#sqlcoptsswarnoncperror) | LMW |
| [ClientCertificate](../../connect/odbc/dsn-connection-string-attribute.md#clientcertificate) | | LMW | 
| [ClientKey](../../connect/odbc/dsn-connection-string-attribute.md#clientkey) | | LMW | 


다음은 [SQL Server Native Client에서 연결 문자열 키워드 사용](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md), [SQLSetConnectAttr](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) 및 [SQLSetConnectAttr Function](../../odbc/reference/syntax/sqlsetconnectattr-function.md)에 나오지 않는 몇 가지 문자열 키워드 및 연결 특성입니다.

### <a name="description"></a>Description

데이터 원본을 설명하는 데 사용됩니다.

### <a name="sql_copt_ss_ansi_oem"></a>SQL_COPT_SS_ANSI_OEM

ANSI에서 OEM으로 데이터 변환을 제어합니다. 

| 특성 값 | Description |
|-|-|
| SQL_AO_OFF | (기본값) 변환이 수행되지 않습니다. |
| SQL_AO_ON | 변환이 수행됩니다. |

### <a name="sql_copt_ss_fallback_connect"></a>SQL_COPT_SS_FALLBACK_CONNECT

SQL Server 대체 연결의 사용을 제어합니다. 이 값은 더 이상 지원되지 않습니다.

| 특성 값 | Description |
|-|-|
| SQL_FB_OFF | (기본값) 대체 연결을 사용하지 않습니다. |
| SQL_FB_ON | (기본값) 대체 연결을 사용합니다. |



## <a name="new-connection-string-keywords-and-connection-attributes"></a>새 연결 문자열 키워드 및 연결 특성

###  <a name="authentication---sql_copt_ss_authentication"></a>Authentication - SQL_COPT_SS_AUTHENTICATION

SQL Server에 연결할 때 사용할 인증 모드를 설정합니다. 자세한 내용은 [Azure Active Directory 사용](using-azure-active-directory.md)을 참조하세요.

| 키워드 값 | 특성 값 | Description |
|-|-|-|
| |SQL_AU_NONE|(기본값) 설정 안 함. 다른 특성의 조합으로 인증 모드를 결정합니다.|
|SqlPassword|SQL_AU_PASSWORD|사용자 이름 및 암호를 사용한 SQL Server 인증|
|ActiveDirectoryIntegrated|SQL_AU_AD_INTEGRATED|Azure Active Directory 통합 인증|
|ActiveDirectoryPassword|SQL_AU_AD_PASSWORD|Azure Active Directory 암호 인증|
|ActiveDirectoryInteractive|SQL_AU_AD_INTERACTIVE|Azure Active Directory 대화형 인증|
|ActiveDirectoryMsi|SQL_AU_AD_MSI|Azure Active Directory 관리 서비스 ID 인증입니다. 사용자 할당 ID의 경우 UID를 사용자 ID의 개체 ID로 설정합니다. |
| |SQL_AU_RESET|설정하지 않습니다. DSN 또는 연결 문자열 설정을 재정의합니다.|

> [!NOTE]
> `Authentication` 키워드 또는 특성을 사용하는 경우 명시적으로 `Encrypt` 설정을 연결 문자열 / DSN / 연결 특성의 원하는 값으로 설정합니다. 자세한 내용은 [SQL Server Native Client에서 연결 문자열 키워드 사용](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)을 참조하세요.

### <a name="columnencryption---sql_copt_ss_column_encryption"></a>ColumnEncryption - SQL_COPT_SS_COLUMN_ENCRYPTION

투명한 열 암호화(Always Encrypted)를 제어합니다. 자세한 내용은 [Always Encrypted 사용(ODBC)](using-always-encrypted-with-the-odbc-driver.md)을 참조하세요.

| 키워드 값 | 특성 값 | Description |
|-|-|-|
|사용|SQL_CE_ENABLED|Always Encrypted를 사용하도록 설정합니다.|
|사용 안 함|SQL_CE_DISABLED|(기본값) Always Encrypted를 사용하지 않도록 설정합니다.|
| |SQL_CE_RESULTSETONLY|암호 해독만 사용하도록 설정합니다(결과 및 반환 값).|

### <a name="transparentnetworkipresolution---sql_copt_ss_tnir"></a>TransparentNetworkIPResolution - SQL_COPT_SS_TNIR

다시 연결 시도가 더 빨리 실행될 수 있도록 MultiSubnetFailover와 상호 작용하는 투명한 네트워크 IP 확인 기능을 제어합니다. 자세한 내용은 [투명 네트워크 IP 확인 사용](using-transparent-network-ip-resolution.md)을 참조하세요.

| 키워드 값 | 특성 값| Description |
|-|-|-|
|사용|SQL_IS_ON|(기본값) 투명 네트워크 IP 확인 사용|
|사용 안 함|SQL_IS_OFF|투명 네트워크 IP 확인 사용 안 함|

### <a name="usefmtonly"></a>UseFMTONLY

SQL Server 2012 이상에 연결할 때 메타데이터에 대한 SET FMTONLY 사용을 제어합니다.

| 키워드 값 | Description |
|-|-|
|예|(기본값) 사용 가능한 경우 메타데이터에 sp_describe_first_result_set을 사용합니다. |
|예| 메타데이터에 SET FMTONLY를 사용합니다. |


## <a name="clientcertificate"></a>ClientCertificate

인증에 사용할 인증서를 지정합니다. 옵션은 다음과 같습니다. 

| 옵션 값 | Description |
|-|-|
| sha1:`<hash_value>` | ODBC 드라이버는 SHA1 해시를 사용하여 Windows 인증서 저장소에서 인증서를 찾습니다. |
| 제목:`<subject>` | ODBC 드라이버는 제목을 사용하여 Windows 인증서 저장소에서 인증서를 찾습니다. |
| 파일:`<file_location>`[,암호:`<password>`] | ODBC 드라이버는 인증서 파일을 사용합니다. |

인증서가 PFX 형식이고 PFX 인증서 내의 프라이빗 키가 암호로 보호되는 경우에는 암호 키워드가 필요합니다. PEM 및 DER 형식의 인증서는 ClientKey 특성이 필요합니다.


## <a name="clientkey"></a>ClientKey

ClientCertificate 특성에 따라 지정된 PEM 또는 DER 인증서에 대해 프라이빗 키의 파일 위치를 지정합니다. 형식: 

| 옵션 값 | Description |
|-|-|
| 파일:`<file_location>`[,암호:`<password>`] | 프라이빗 키 파일의 위치를 지정합니다. |

프라이빗 키 파일이 암호로 보호되는 경우에는 암호 키워드가 필요합니다. 암호에 "," 문자가 포함된 경우, 각 문자 바로 뒤에 "," 문자가 더 추가됩니다. 예를 들어 암호가 "a,b,c"라면 해당 문자열에 있는 이스케이프된 암호는 "a,,b,,c"입니다. 
    

### <a name="sql_copt_ss_access_token"></a>SQL_COPT_SS_ACCESS_TOKEN

인증에 Azure Active Directory 액세스 토큰을 사용하도록 허용합니다. 자세한 내용은 [Azure Active Directory 사용](using-azure-active-directory.md)을 참조하세요.

| 특성 값 | Description |
|-|-|
| NULL | (기본값) 액세스 토큰을 제공하지 않습니다. |
| ACCESSTOKEN* | 액세스 토큰 포인터입니다. |

### <a name="sql_copt_ss_cekeystoredata"></a>SQL_COPT_SS_CEKEYSTOREDATA

로드된 키 저장소 공급자 라이브러리와 통신합니다. 투명한 열 암호화(Always Encrypted) 제어를 참조하세요. 이 특성에는 기본값이 없습니다. 자세한 내용은 [사용자 지정 키 저장소 공급자](custom-keystore-providers.md)를 참조하세요.

| 특성 값 | Description |
|-|-|
| CEKEYSTOREDATA * | 키 저장소 라이브러리에 대한 통신 데이터 구조 |

### <a name="sql_copt_ss_cekeystoreprovider"></a>SQL_COPT_SS_CEKEYSTOREPROVIDER

Always Encrypted용 키 저장소 공급자 라이브러리를 로드하거나 로드된 키 저장소 공급자 라이브러리의 이름을 검색합니다. 자세한 내용은 [사용자 지정 키 저장소 공급자](custom-keystore-providers.md)를 참조하세요. 이 특성에는 기본값이 없습니다.

| 특성 값 | Description |
|-|-|
| char * | 키 저장소 공급자 라이브러리에 대한 경로 |

### <a name="sql_copt_ss_enlist_in_xa"></a>SQL_COPT_SS_ENLIST_IN_XA

XA 규정 준수 TP(트랜잭션 프로세서)에서 XA 트랜잭션을 사용하도록 설정하려면 애플리케이션에서 SQL_COPT_SS_ENLIST_IN_XA 및 `XACALLPARAM` 개체 포인터를 사용하여 **SQLSetConnectAttr**을 호출해야 합니다. 이 옵션은 Windows, Linux(17.3 이상) 및 macOS에서 지원됩니다.
```
SQLSetConnectAttr(hdbc, SQL_COPT_SS_ENLIST_IN_XA, param, SQL_IS_POINTER);  // XACALLPARAM *param
``` 
 XA 트랜잭션을 ODBC 연결에만 연결하려면 **SQLSetConnectAttr**을 호출할 때 포인터 대신에 SQL_COPT_SS_ENLIST_IN_XA를 사용하여 TRUE 또는 FALSE를 제공합니다. 이 방법은 Windows에서만 유효하며 클라이언트 애플리케이션을 통해 XA 작업을 지정하는 데 사용할 수 없습니다. 
 ```
SQLSetConnectAttr(hdbc, SQL_COPT_SS_ENLIST_IN_XA, (SQLPOINTER)TRUE, 0);
``` 

|값|Description|플랫폼|  
|-----------|-----------------|-----------------|  
|XACALLPARAM 개체*|`XACALLPARAM` 개체에 대한 포인터입니다.|Windows, Linux 및 macOS|
|TRUE|XA 트랜잭션을 ODBC 연결과 연결합니다. 관련된 모든 데이터베이스 작업은 XA 트랜잭션의 보호 아래 수행됩니다.|Windows|  
|FALSE|ODBC 연결과 트랜잭션의 연결을 해제합니다.|Windows|

 XA 트랜잭션에 대한 자세한 내용은 [XA 트랜잭션 사용](../../connect/odbc/use-xa-with-dtc.md)을 참조하세요.

### <a name="sql_copt_ss_spid"></a>SQL_COPT_SS_SPID

연결의 서버 프로세스 ID를 검색합니다. 이는 서버에 대한 라운드트립이 추가로 발생하지 않는다는 점을 제외하고는 T-SQL [@@SPID](../../t-sql/functions/spid-transact-sql.md) 변수와 같습니다.

| 특성 값 | Description |
|-|-|
| DWORD | SPID |
