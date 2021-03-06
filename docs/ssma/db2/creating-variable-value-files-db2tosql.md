---
title: 변수 값 파일 만들기 (DB2ToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 122f3fbe-46a0-40df-ac3b-d43bf33d96ba
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 945b7e86641c796e79bfb87b8b7b5de25949e4c2
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "67989773"
---
# <a name="creating-variable-value-files-db2tosql"></a>변수 값 파일 만들기 (DB2ToSQL)
변수 값 파일은 서버 마이그레이션 간에 자주 변경 되는 원본 또는 대상 서버 이름과 같은 명령의 매개 변수 값을 구성 하는 XML 파일입니다. 데이터베이스 마이그레이션이 많은 경우 각 원본 서버의 값을 저장 하는 여러 변수 파일이 생성 되 고 명령줄에서 **-v** 스위치를 사용 하 여 마스터 스크립트 파일에서 참조 됩니다. 이를 통해 여러 변수 파일의 변수 값을 사용 하 여 몇 가지 스크립트 파일의 정적 값을 유지 관리할 수 있습니다.  
  
> [!NOTE]  
> 1.  변수 이름 앞에는 $ (달러) 기호가 붙습니다. 변수에 변수 값 파일의 값이 할당 되지 않은 경우에는 스크립트 파일을 구문 분석 하는 동안 오류가 발생 하 여 콘솔 실행 프로세스가 상태일 됩니다.  
> 2.  에 대 한 **$** 이스케이프 문자 **$$** 는입니다. 매개 변수의 변수 또는 정적 값이 (달러) 기호를 포함 **$** 하는 경우 변수 대신 문자로 **$$** 처리 하도록를 지정 해야 합니다.  
> 3.  유지 관리를 위해 변수를 요소 내 `'variable-group'` 에 선언 하 여 사용자 정의 변수의 논리적 분리를 수행할 수 있습니다.  이 요소는 반드시 사용 해야 하는 것은 아닙니다.  
  
**예:**  
  
**예 1:**  
  
```  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="ProjectSpecs">  
  
    <variable name="$project_folder$" value="<project-folder>"/>  
  
    <variable name="$project_name$" value="<project-name>"/>  
  
    <variable name="$project_overwrite$" value="<true/false>"/>  
  
    <variable name="$project_type$" value="<project-type>"/>  
  
  </variable-group>  
  
</variables>  
```  
**예 2:**  
  
```  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="SQLServerParams">  
  
    <variable-group name="SqlServerConnectionParams">  
  
      <variable name="$TargetServerName$" value="<server-name>"/>  
  
      <variable name="$TargetDB$" value="<database-name>"/>  
  
      <variable name="$TargetUserName$" value="<user-name>"/>  
  
      <variable name="$TargetPassword$" value="<password>"/>  
  
      <variable name="$TrustedConnection$" value="<true/false>"/>  
  
    </variable-group>  
  
    <variable-group name="SqlServerObjectParams">  
  
      <variable name="$ObjectName1$" value="<object-name>"/>  
  
      <variable name="$ObjectName2$" value="<object-name>"/>  
  
    </variable-group>  
  
  </variable-group>  
  
</variables>  
```  
  
## <a name="next-step"></a>다음 단계  
콘솔 운영의 다음 단계에서는 [DB2ToSQL &#40;서버 연결 파일을 만듭니다&#41;](../../ssma/db2/creating-the-server-connection-files-db2tosql.md)  
  
## <a name="see-also"></a>참고 항목  
[서버 연결 파일 만들기](../oracle/creating-the-server-connection-files-oracletosql.md)  
  
