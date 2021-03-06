---
title: Precision 속성 (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Column::put_Precision
- _Column::PutPrecision
- _Column::GetPrecision
- _Column::get_Precision
- _Column::Precision
helpviewer_keywords:
- Precision property [ADOX]
ms.assetid: 0e0ecbbf-d7de-49d4-a128-5a519ecd54ba
author: rothja
ms.author: jroth
ms.openlocfilehash: 67512b74e4c2b869cb7b1f9397462ce5566557a8
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763724"
---
# <a name="precision-property-adox"></a>Precision 속성(ADOX)
[열](../../../ado/reference/adox-api/column-object-adox.md)에 있는 데이터 값의 최대 전체 자릿수를 나타냅니다.  
  
## <a name="settings-and-return-values"></a>설정 및 반환 값  
 [Type](../../../ado/reference/adox-api/type-property-column-adox.md) 속성이 숫자 형식인 경우 열에 있는 데이터 값의 최대 전체 자릿수 인 **Long** 값을 설정 하 고 반환 합니다. 다른 모든 데이터 형식에 대해서는 **전체 자릿수가** 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 기본값은 영(**0**)입니다.  
  
 컬렉션에 이미 추가 된 [열](../../../ado/reference/adox-api/column-object-adox.md) 개체의 경우이 속성은 읽기 전용입니다.  
  
## <a name="applies-to"></a>적용 대상  
 [Column 개체(ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>참고 항목  
 [ADOX 코드 예제: NumericScale 및 Precision 속성 예제 (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type 속성 (Column) (ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)   
 [Column 개체(ADOX)](../../../ado/reference/adox-api/column-object-adox.md)
