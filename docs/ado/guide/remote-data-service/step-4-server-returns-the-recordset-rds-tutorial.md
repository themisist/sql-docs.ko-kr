---
title: '4 단계: 서버가 레코드 집합을 반환 합니다 (RDS 자습서). | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], server returns Recordset
ms.assetid: 3d1855c4-419c-4810-b5ea-6c874b5e2905
author: rothja
ms.author: jroth
ms.openlocfilehash: ce53c987a43ed208a4d7120fb3655b3a3acd5083
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764664"
---
# <a name="step-4-server-returns-the-recordset-rds-tutorial"></a>4단계: 서버가 레코드 집합을 반환합니다(RDS 자습서).
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012부터 RDS 서버 구성 요소는 더 이상 Windows 운영 체제에 포함 되지 않습니다 (자세한 내용은 Windows 8 및 [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) 참조). 이후 버전의 Windows에서는 RDS 클라이언트 구성 요소가 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 애플리케이션은 수정하세요. RDS를 사용 하는 응용 프로그램은 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)로 마이그레이션해야 합니다.  
  
 RDS는 검색 된 **레코드 집합** 개체를 클라이언트로 다시 보낼 수 있는 형식으로 변환 합니다. 즉, **레코드 집합**을 *마샬링합니다* . 변환의 정확한 형태 및 전송 방법은 서버가 인터넷에 있는지 인트라넷에 있는지 인트라넷에 있는지 또는 인트라넷에 있는지 또는 동적 연결 라이브러리에 있는지에 따라 다릅니다. 그러나이 세부 정보는 중요 하지 않습니다. 이러한 모든 것이 중요 한 것은 RDS에서 **레코드 집합** 을 클라이언트로 다시 보내는 것입니다.  
  
 클라이언트 쪽에서 **레코드 집합** 개체가 반환 되 고 지역 변수에 할당 됩니다.  
  
```vb
Sub RDSTutorial4()  
   Dim DS as New RDS.DataSpace  
   Dim RS as ADODB.Recordset  
   Dim DF as Object  
   Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer")  
   Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors")  
...  
```  
  
## <a name="see-also"></a>참고 항목  
 [5 단계: DataControl을 사용할 수 있습니다 (RDS 자습서).](../../../ado/guide/remote-data-service/step-5-datacontrol-is-made-usable-rds-tutorial.md)   
 [RDS 자습서(VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
