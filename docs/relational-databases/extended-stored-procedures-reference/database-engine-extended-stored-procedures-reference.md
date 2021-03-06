---
title: 확장 저장 프로시저 프로그래머 참조 | Microsoft Docs
description: 데이터베이스 엔진 확장 저장 프로시저에서 SQL Server 기능을 확장 하기 위한 서버 기반 API (응용 프로그래밍 인터페이스)를 제공 하는 방법에 대해 알아봅니다.
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], listed
ms.assetid: 4e9d0374-0927-4f17-bab9-2215b1b8fea8
author: rothja
ms.author: jroth
ms.openlocfilehash: a2830f920078a4e625e9ccf0fc13f376b3fd4107
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87244020"
---
# <a name="database-engine-extended-stored-procedures---reference"></a>데이터베이스 엔진 확장 저장 프로시저 - 참조
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 대신 CLR 통합을 사용하세요.  
  
 이전에 개방형 Data Services의 일부였던 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 확장 저장 프로시저 API는 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 기능을 확장하기 위한 서버 기반 API(애플리케이션 프로그래밍 인터페이스)를 제공합니다. API는 애플리케이션을 빌드하는 데 사용되는 C 및 C++ 함수와 매크로로 구성됩니다.  
  
 CLR 통합과 같은 보다 강력한 최신 기술이 등장하면서 확장 저장 프로시저의 필요성이 크게 바뀌었습니다.  
  
> [!IMPORTANT]  
>  확장 저장 프로시저의 원본 코드를 철저히 검토하고 프로덕션 서버에 DLL을 설치하기 전에 컴파일한 DLL을 테스트해야 합니다. 보안 검토 및 테스트에 대한 자세한 내용은 [Microsoft 웹 사이트](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/)를 참조하십시오.  
  
## <a name="in-this-section"></a>섹션 내용  
  
:::row:::
    :::column:::
        [데이터 형식](../../relational-databases/extended-stored-procedures-reference/data-types-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_pfield](../../relational-databases/extended-stored-procedures-reference/srv-pfield-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_alloc](../../relational-databases/extended-stored-procedures-reference/srv-alloc-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_convert](../../relational-databases/extended-stored-procedures-reference/srv-convert-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_pfieldex](../../relational-databases/extended-stored-procedures-reference/srv-pfieldex-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_describe](../../relational-databases/extended-stored-procedures-reference/srv-describe-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_rpcdb](../../relational-databases/extended-stored-procedures-reference/srv-rpcdb-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_getbindtoken](../../relational-databases/extended-stored-procedures-reference/srv-getbindtoken-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_rpcname](../../relational-databases/extended-stored-procedures-reference/srv-rpcname-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_got_attention](../../relational-databases/extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_rpcnumber](../../relational-databases/extended-stored-procedures-reference/srv-rpcnumber-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
    :::column-end:::
    :::column:::
        [srv_rpcoptions](../../relational-databases/extended-stored-procedures-reference/srv-rpcoptions-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_message_handler](../../relational-databases/extended-stored-procedures-reference/srv-message-handler-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_rpcowner](../../relational-databases/extended-stored-procedures-reference/srv-rpcowner-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramdata](../../relational-databases/extended-stored-procedures-reference/srv-paramdata-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_rpcparams](../../relational-databases/extended-stored-procedures-reference/srv-rpcparams-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paraminfo](../../relational-databases/extended-stored-procedures-reference/srv-paraminfo-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_senddone](../../relational-databases/extended-stored-procedures-reference/srv-senddone-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramlen](../../relational-databases/extended-stored-procedures-reference/srv-paramlen-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_sendmsg](../../relational-databases/extended-stored-procedures-reference/srv-sendmsg-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_parammaxlen](../../relational-databases/extended-stored-procedures-reference/srv-parammaxlen-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_sendrow](../../relational-databases/extended-stored-procedures-reference/srv-sendrow-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramname](../../relational-databases/extended-stored-procedures-reference/srv-paramname-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_setcoldata](../../relational-databases/extended-stored-procedures-reference/srv-setcoldata-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramnumber](../../relational-databases/extended-stored-procedures-reference/srv-paramnumber-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_setcollen](../../relational-databases/extended-stored-procedures-reference/srv-setcollen-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramset](../../relational-databases/extended-stored-procedures-reference/srv-paramset-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_setutype](../../relational-databases/extended-stored-procedures-reference/srv-setutype-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramsetoutput](../../relational-databases/extended-stored-procedures-reference/srv-paramsetoutput-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_willconvert](../../relational-databases/extended-stored-procedures-reference/srv-willconvert-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramstatus](../../relational-databases/extended-stored-procedures-reference/srv-paramstatus-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
        [srv_wsendmsg](../../relational-databases/extended-stored-procedures-reference/srv-wsendmsg-extended-stored-procedure-api.md)
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        [srv_paramtype](../../relational-databases/extended-stored-procedures-reference/srv-paramtype-extended-stored-procedure-api.md)
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::
  
