---
title: CursorOptionEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CursorOptionEnum
helpviewer_keywords:
- CursorOptionEnum enumeration [ADO]
ms.assetid: 4e10cda7-ce81-4466-94c2-844d38191cf1
author: rothja
ms.author: jroth
ms.openlocfilehash: d7ac2825c5b700c7c9855f554cdd76cfd28547bd
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763522"
---
# <a name="cursoroptionenum"></a>CursorOptionEnum
에서 [지원](../../../ado/reference/ado-api/supports-method.md) 되는 메서드가 테스트할 기능을 지정 합니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|**adAddNew**|0x1000400|[AddNew](../../../ado/reference/ado-api/addnew-method-ado.md) 메서드를 지원 하 여 새 레코드를 추가 합니다.|  
|**adApproxPosition**|0x4000|[AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md) 및 [AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md) 속성을 지원 합니다.|  
|**adBookmark**|0x2000|는 특정 레코드에 대 한 액세스 권한을 얻기 위해 [Bookmark](../../../ado/reference/ado-api/bookmark-property-ado.md) 속성을 지원 합니다.|  
|**adDelete**|0x1000800|레코드 삭제를 위한 [delete](../../../ado/reference/ado-api/delete-method-ado-recordset.md) 메서드를 지원 합니다.|  
|**adFind**|0x80000|는 [Find](../../../ado/reference/ado-api/find-method-ado.md) 메서드를 지원 하 여 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md)의 행을 찾습니다.|  
|**adHoldRecords**|0x100|더 많은 레코드를 검색 하거나 보류 중인 모든 변경 내용을 커밋하지 않고 다음 위치를 변경 합니다.|  
|**adIndex**|0x100000|인덱스 속성 [을 지원 하 여 인덱스](../../../ado/reference/ado-api/index-property.md) 이름을 지원 합니다.|  
|**adMovePrevious**|0x200|는 [MoveFirst](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 및 [MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 메서드와 [move](../../../ado/reference/ado-api/move-method-ado.md) 또는 [GetRows](../../../ado/reference/ado-api/getrows-method-ado.md) 메서드를 지원 하 여 책갈피를 요구 하지 않고 현재 레코드 위치를 뒤로 이동 합니다.|  
|**adNotify**|0x40000|기본 데이터 공급자가 **레코드 집합** 이벤트가 지원 되는지 여부를 확인 하는 알림을 지원 함을 나타냅니다.|  
|**adResync**|0x20000|기본 데이터베이스에 표시 되는 데이터로 커서를 업데이트 하는 [Resync](../../../ado/reference/ado-api/resync-method.md) 메서드를 지원 합니다.|  
|**adSeek**|0x200000|[검색](../../../ado/reference/ado-api/seek-method.md) 메서드를 지원 하 여 **레코드 집합**의 행을 찾습니다.|  
|**adUpdate**|0x1008000|기존 데이터를 수정 하는 [Update](../../../ado/reference/ado-api/update-method.md) 메서드를 지원 합니다.|  
|**adUpdateBatch**|0x10000|일괄 처리 업데이트 ([UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) 및 [CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md) 메서드)를 지원 하 여 변경 그룹을 공급자에 게 전송 합니다.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 동급  
 Package: **com.ms.wfc.data**  
  
|상수|  
|--------------|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums.CursorOption.HOLDRECORDS|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption. MOVEPREVIOUS|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
|AdoEnums. CursorOption|  
  
## <a name="applies-to"></a>적용 대상  
 [Supports 메서드](../../../ado/reference/ado-api/supports-method.md)
