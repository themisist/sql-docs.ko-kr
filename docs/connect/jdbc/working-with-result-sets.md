---
title: 결과 집합 작업 | Microsoft Docs
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 4fc4b1c6-3075-4ad7-9244-865d9ede7ae6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f29e7e101a0a295266ee5cfa96fbaa84f515e776
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923895"
---
# <a name="working-with-result-sets"></a>결과 집합 작업

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 포함된 데이터를 사용하는 경우 데이터 조작 방법 중 하나가 결과 집합을 사용하는 것입니다. [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]에서는 [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md) 개체를 통해 결과 집합을 사용할 수 있습니다. SQLServerResultSet 개체를 사용하면 SQL 문이나 저장 프로시저에서 반환된 데이터를 검색하고 필요에 따라 해당 데이터를 업데이트한 후 데이터베이스에 다시 보관할 수 있습니다.  
  
또한 SQLServerResultSet 개체는 데이터 행을 탐색하고 포함된 데이터를 수집 또는 설정하며 기본 데이터베이스의 변경 내용에 따라 중요도 수준을 다양하게 설정할 수 있는 메서드를 제공합니다.  
  
> [!NOTE]  
> 변경 내용에 따른 민감도를 포함하여 결과 집합에 대한 자세한 내용은 [JDBC 드라이버로 결과 집합 관리](../../connect/jdbc/managing-result-sets-with-the-jdbc-driver.md)를 참조하세요.  
  
이 섹션의 항목에서는 결과 집합을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 포함된 데이터를 조작하는 다양한 방법에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
| 항목                                                                                        | Description                                                                                                                                                                                          |
| -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [결과 집합 데이터 검색 샘플](../../connect/jdbc/retrieving-result-set-data-sample.md) | 결과 집합을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에서 데이터를 검색하고 이를 표시하는 방법을 설명합니다.                                                         |
| [결과 집합 데이터 수정 샘플](../../connect/jdbc/modifying-result-set-data-sample.md)   | 결과 집합을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에서 데이터를 삽입, 검색 및 수정하는 방법을 설명합니다.                                                      |
| [결과 집합 데이터 캐싱 샘플](../../connect/jdbc/caching-result-set-data-sample.md)       | 결과 집합을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에서 대량의 데이터를 검색하고 클라이언트에서 해당 데이터가 캐시되는 방식을 제어하는 방법을 설명합니다. |
  
## <a name="see-also"></a>참고 항목

 [샘플 JDBC 드라이버 애플리케이션](../../connect/jdbc/sample-jdbc-driver-applications.md)  
  
