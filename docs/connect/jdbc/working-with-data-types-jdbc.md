---
title: 데이터 형식(JDBC) 사용 | Microsoft Docs
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: b39f44d0-3710-4bc6-880c-35bd8c10a734
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5d5f4414e596ab59f33ab73b6d01908b16d89b24
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923920"
---
# <a name="working-with-data-types-jdbc"></a>데이터 형식 사용(JDBC)

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]의 기본 기능은 Java 개발자가 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 포함된 데이터에 액세스할 수 있게 하는 것입니다. 이를 위해 JDBC 드라이버는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식과 Java 언어 형식 및 개체 사이의 변환을 중재합니다.  
  
> [!NOTE]  
> 형식 간 차이점 및 Java 언어 데이터 형식으로 변환하는 방법에 대한 내용을 포함한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 및 JDBC 드라이버 데이터 형식에 대한 자세한 내용은 [JDBC 드라이버 데이터 형식 이해](../../connect/jdbc/understanding-the-jdbc-driver-data-types.md)를 참조하세요.  
  
SQL Server 데이터 형식 작업을 위해 JDBC 드라이버에서는 [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 및 [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) 클래스에 대해 get\<Type> 및 set\<Type> 메서드를 제공하며, [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md) 클래스에 대해 get\<Type> 및 update\<Type> 메서드를 제공합니다. 어떤 메서드를 사용할지는 작업하는 데이터 형식 및 결과 집합이나 쿼리 사용 여부에 따라 달라집니다.  
  
이 섹션의 항목에서는 JDBC 드라이버 데이터 형식을 사용하여 Java 애플리케이션의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터에 액세스하는 방법을 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|항목|Description|  
|-----------|-----------------|  
|[기본 데이터 형식 샘플](../../connect/jdbc/basic-data-types-sample.md)|결과 집합 getter 메서드를 사용하여 기본 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식 값을 검색하는 방법 및 결과 집합 업데이트 메서드를 사용하여 이러한 값을 업데이트하는 방법을 설명합니다.|  
|[SQLXML 데이터 형식 샘플](../../connect/jdbc/sqlxml-data-type-sample.md)|XML 데이터를 관계형 데이터베이스에 저장하는 방법, XML 데이터를 데이터베이스에서 검색하는 방법 및 **SQLXML** Java 데이터 형식으로 XML 데이터를 구문 분석하는 방법을 보여 줍니다.|  
|[공간 데이터 형식 샘플](../../connect/jdbc/spatial-data-types-sample.md)|Microsoft JDBC 드라이버에서 정의된 **Geometry** 및 **Geography** Java 형식이 포함된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에서 공간 데이터 형식 ‘Geometry’ 및 ‘Geography’를 사용하여 데이터를 저장하고 검색하는 방법을 설명합니다.|

## <a name="see-also"></a>참고 항목

[샘플 JDBC 드라이버 애플리케이션](../../connect/jdbc/sample-jdbc-driver-applications.md)  
