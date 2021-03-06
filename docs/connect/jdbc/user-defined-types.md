---
title: 사용자 정의 형식 | Microsoft Docs
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 19a71b27-b788-43a3-a76d-fe3001a6f016
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9ce45cb7fb76c1b01b57d96d86e34b051dc73043
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80916949"
---
# <a name="user-defined-types"></a>사용자 정의 형식

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

UDT(사용자 정의 형식)는 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]에서 도입된 것으로, 개발자가 CLR(공용 언어 런타임) 개체를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스에 저장하여 서버의 스칼라 형식 시스템을 확장할 수 있도록 합니다. UDT는 단일 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시스템 데이터 형식으로 구성된 일반적인 별칭 데이터 형식과 달리 여러 요소를 포함할 수 있으며 관련 동작이 있을 수 있습니다. 이전에는 UDT의 최대 크기가 8KB로 제한되었습니다. [!INCLUDE[ssKatmai](../../includes/sskatmai_md.md)]에서 64킬로바이트를 초과하는 크기의 UDT에 대한 지원이 추가되었습니다. UserDefined 형식을 지정하는 경우 버전 3.0부터 JDBC 드라이버는 이제 64KB를 초과하는 UDT도 지원합니다.

8,000바이트보다 작거나 같은 UDT의 동작에는 변경된 사항이 없지만 이보다 큰 UDT도 지원되며 이 경우 크기가 "제한 없음"으로 보고됩니다.

## <a name="see-also"></a>참고 항목

[JDBC 드라이버 데이터 형식 이해](../../connect/jdbc/understanding-the-jdbc-driver-data-types.md)
