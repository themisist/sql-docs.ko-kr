---
title: UDT(사용자 정의 데이터 형식)에 대한 FOR XML 지원 | Microsoft Docs
description: FOR XML 절을 사용할 때의 UDT(사용자 정의 데이터 형식) 지원에 관해 알아봅니다.
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- UDTs [SQL Server], XML
- user-defined types [SQL Server], XML
ms.assetid: 354e2150-fa2a-4583-b1aa-6b78ae4378b6
author: MightyPen
ms.author: genemi
ms.custom: seo-lt-2019
ms.openlocfilehash: 53a70da583b55fa8d979aeaaee3782fd6551c6ea
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85729922"
---
# <a name="for-xml-support-for-the-user-defined-data-types-udt"></a>사용자 정의 데이터 형식(UDT)에 대한 FOR XML 지원
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  FOR XML은 CLR(공용 언어 런타임) UDT(사용자 정의 데이터 형식)를 지원하지 않습니다.  
  
 CLR 사용자 정의 데이터 형식으로 FOR XML을 사용하려면 데이터 형식에 XML 직렬화가 있는지 확인하고 FOR XML 선택 절의 XML로의 명시적 캐스트를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다양한 SQL Server 데이터 형식에 대한 FOR XML 지원](../../relational-databases/xml/for-xml-support-for-various-sql-server-data-types.md)  
  
  
