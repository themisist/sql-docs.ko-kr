---
title: 테이블 반환 매개 변수 형식 검색 | Microsoft Docs
description: OLE DB Driver for SQL Server를 사용하여 테이블 반환 매개 변수 형식 검색
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
author: pmasl
ms.author: pelopes
ms.openlocfilehash: 06e0de0ad5fb0b4b8b7fd90144769ca9f9133928
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86003331"
---
# <a name="table-valued-parameter-type-discovery"></a>테이블 반환 매개 변수 형식 검색
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  소비자(SQL Server용 OLE DB 드라이버를 사용하는 클라이언트 애플리케이션)는 OLE DB 공급자에 명령 텍스트가 지정되어 있는 경우 각 명령 매개 변수의 형식을 검색할 수 있습니다. 테이블 반환 매개 변수의 형식이 확인되면 소비자가 테이블 반환 매개 변수의 개별 열에 대한 메타데이터 정보를 검색할 수 있습니다.  
  
 프로시저 매개 변수의 형식 정보는 대부분의 매개 변수 형식에서 ICommandWithParameters::GetParameterInfo를 통해 지원됩니다. [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]부터 사용자 정의 형식과 **xml** 데이터 형식이 도입되면서 GetParameterInfo 메서드는 ICommandWithParameters를 통해 사용자 정의 형식 정보(이름, 스키마 및 카탈로그)를 제공할 수 없으므로 이러한 용도에 적합하지 않게 되었습니다. 따라서 확장된 형식 정보를 제공하기 위해 새로운 인터페이스인 ISSCommandWithParameters가 정의되었습니다.  
  
 테이블 반환 매개 변수의 경우 ISSCommandWithParameters 인터페이스를 사용하여 자세한 정보를 검색할 수도 있습니다. 명령 개체를 준비하고 나면 클라이언트가 ISSCommandWithParameters::GetParameterInfo를 호출합니다. 테이블 반환 매개 변수의 경우 공급자에 의해 DBPARAMINFO 구조의 *wType* 멤버가 DBTYPE_TABLE로 설정됩니다. DBPARAMINFO 구조의 *ulParamSize* 필드 값은 ~0입니다.  
  
 그런 다음, 소비자는 ISSCommandWithParameters::GetParameterProperties를 사용하여 추가 속성(테이블 반환 매개 변수 형식 카탈로그 이름, 테이블 반환 매개 변수 형식 스키마 이름, 테이블 반환 매개 변수 형식 이름, 열 순서 및 기본 열)을 요청합니다.  
  
 형식 이름이 확인되면 소비자는 IOpenRowset::OpenRowsetor를 호출하거나 테이블 반환 매개 변수 형식 이름을 테이블 이름으로 지정하여 DBSCHEMA_TABLE_TYPE_COLUMNS 행 집합을 가져옴으로써 개별 열 정보를 검색해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [테이블 반환 매개 변수&#40;OLE DB&#41;](../../oledb/ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)   
 [테이블 반환 매개 변수&#40;OLE DB&#41; 사용](../../oledb/ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
