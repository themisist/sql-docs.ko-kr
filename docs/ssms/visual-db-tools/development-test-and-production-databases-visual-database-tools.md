---
title: 개발, 테스트 및 프로덕션 데이터베이스
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- production databases [SQL Server]
- testing databases
- database testing [SQL Server]
ms.assetid: cb403330-8cbe-41c6-bd23-bc432d50f173
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.openlocfilehash: e0f50cc149c592633969c84a8f541239d55f1240
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "85987093"
---
# <a name="development-test-and-production-databases-visual-database-tools"></a>개발, 테스트 및 프로덕션 데이터베이스(Visual Database Tools)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
동일한 구조의 데이터베이스가 두 개 있으면 한 데이터베이스에서 변경한 내용을 다른 데이터베이스로 전파할 수 있습니다. 예를 들어, 개인 개발 데이터베이스와 그룹 범위의 테스트 데이터베이스가 있는 경우 개발 데이터베이스를 수정한 다음 해당 수정 내용을 테스트 데이터베이스로 전파할 수 있습니다.  
  
이를 위해서는 개발 데이터베이스를 사용하여 단일 세션에서 모든 수정 작업을 수행하고 해당 세션에 대한 변경 스크립트를 만든 다음 테스트 데이터베이스에 대해 이 스크립트를 실행해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
[다중 사용자 환경&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/multiuser-environments-visual-database-tools.md)  
  
