---
title: 테이블 반환 매개 변수에 영향을 주는 특성
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), descriptor header field
- table-valued parameters (ODBC), statement attribute
ms.assetid: 089213b0-d368-4332-b2e5-b2bd8770c64f
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 71f43396dee59a62b68c774533340d86da0fe9f4
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "85998372"
---
# <a name="statement-attributes-that-affect-table-valued-parameters"></a>테이블 반환 매개 변수에 영향을 주는 문 특성
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  다음 표에서는 설명자 필드의 특성을 설명합니다.  
  
|특성 이름|Type|Description|  
|--------------------|----------|-----------------|  
|SQL_SOPT_SS_PARAM_FOCUS|SQLUINTEGER|SQL_SS_PARAM_FOCUS에 대 한 자세한 내용은 [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)를 참조 하세요.|  
|SQL_SOPT_SS_NAME_SCOPE|SQLUINTEGER|SQL_SS_NAME_SCOPE에 대 한 자세한 내용은 [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)를 참조 하세요.|  
||||

## <a name="see-also"></a>참고 항목  
 [ODBC&#41;&#40;테이블 반환 매개 변수](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
  
