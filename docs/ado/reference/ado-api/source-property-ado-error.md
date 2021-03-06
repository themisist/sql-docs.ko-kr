---
title: Source 속성 (ADO 오류) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Error::get_Source
- Error::Source
- Error::GetSource
helpviewer_keywords:
- Source property [ADO Error]
ms.assetid: 4044ba15-f013-4c4c-9fe1-b4410fe9a778
author: rothja
ms.author: jroth
ms.openlocfilehash: 95b000db970bc3da925319bbe6e273557a8787ca
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759829"
---
# <a name="source-property-ado-error"></a>Source 속성(ADO 오류)
원래 오류를 생성 한 개체 또는 응용 프로그램의 이름을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 개체 또는 응용 프로그램의 이름을 나타내는 **문자열** 값을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 [오류](../../../ado/reference/ado-api/error-object.md) 개체의 **Source** 속성을 사용 하 여 원래 오류를 생성 한 개체 또는 응용 프로그램의 이름을 확인 합니다. 개체의 클래스 이름 또는 프로그래밍 ID 일 수 있습니다. ADO의 오류에 대 한 속성 값은 **ADODB입니다.** _Objectname_. 여기서 *objectname* 은 오류를 트리거한 개체의 이름입니다. ADOX 및 ADO MD의 경우 값은 Adox가 됩니다 **.** _ObjectName_ 및 **ADOMD.** _ObjectName_각각.  
  
 **오류 개체의** **Source**, [Number](../../../ado/reference/ado-api/number-property-ado.md)및 [Description](../../../ado/reference/ado-api/description-property.md) 속성에 있는 오류 설명서를 기반으로 오류를 적절 하 게 처리 하는 코드를 작성할 수 있습니다.  
  
 **원본** 속성은 **오류** 개체에 대 한 읽기 전용입니다.  
  
## <a name="applies-to"></a>적용 대상  
 [Error 개체](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>참고 항목  
 [Description, HelpContext, HelpFile, NativeError, Number, Source 및 SQLState 속성 예제 (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Description, HelpContext, HelpFile, NativeError, Number, Source 및 SQLState 속성 예제 (VC + +)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Description 속성](../../../ado/reference/ado-api/description-property.md)   
 [HelpContext, HelpFile 속성](../../../ado/reference/ado-api/helpcontext-helpfile-properties.md)   
 [Number 속성 (ADO)](../../../ado/reference/ado-api/number-property-ado.md)   
 [Source 속성 (ADO 레코드)](../../../ado/reference/ado-api/source-property-ado-record.md)   
 [Source 속성(ADO 레코드 집합)](../../../ado/reference/ado-api/source-property-ado-recordset.md)
