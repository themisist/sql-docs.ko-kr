---
title: RDS에서 &quot; 읽기 불가능 한 스트림 반환 &quot; 오류 | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stream not read error in RDS [ADO]
ms.assetid: cb5a68f8-dba4-41da-bafd-04efe53706b7
author: rothja
ms.author: jroth
ms.openlocfilehash: ca194c911b590dfcc8baba87195c91a70640dd24
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82747735"
---
# <a name="rds-returns-quotstream-not-readquot-error"></a>RDS 반환 &quot; 스트림 읽기 &quot; 오류
"스트림 개체는 비어 있거나 현재 위치가 스트림의 끝에 있기 때문에 읽을 수 없습니다. 비어 있지 않은 스트림의 경우 Position 속성을 사용 하 여 현재 위치를 설정 합니다. 스트림이 비어 있는지 확인 하려면 Size 속성을 확인 하십시오.  
  
 이 오류 메시지가 표시 되 면 http를 통해 매개 변수가 있는 계층적 쿼리를 사용 하려고 했을 수 있습니다. RDS에서는 매개 변수가 있는 원격 계층을 사용할 수 없습니다.  
  
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012부터 RDS 서버 구성 요소는 더 이상 Windows 운영 체제에 포함 되지 않습니다 (자세한 내용은 Windows 8 및 [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) 참조). 이후 버전의 Windows에서는 RDS 클라이언트 구성 요소가 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 애플리케이션은 수정하세요. RDS를 사용 하는 응용 프로그램은 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)로 마이그레이션해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [RDS 기본 사항](../../../ado/guide/remote-data-service/rds-fundamentals.md)


