---
title: 업데이트할 수 있는 구독 | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cf65d8667e0fcedcb148e926a80969ec7a05642
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85720670"
---
# <a name="updatable-subscriptions"></a>업데이트할 수 있는 구독
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  복제된 데이터는 읽기 전용으로 취급되어야 하지만 트랜잭션 복제를 사용하면 업데이트할 수 있는 구독을 사용하여 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구독자에서 복제된 데이터를 수정할 수 있습니다. 구독자에서 데이터를 수정해야 하는 경우 요구 사항에 따라 다음 옵션 중 하나를 선택합니다.  
  
|업데이트할 수 있는 구독 유형|요구 사항|  
|---------------------------------|------------------|  
|즉시 업데이트|구독자에서 데이터를 업데이트하기 위해 게시자 및 구독자를 연결해야 합니다.|  
|지연 업데이트|구독자에서 데이터를 업데이트하기 위해 게시자 및 구독자를 연결할 필요가 없습니다. 오프라인 상태에서 업데이트한 다음 나중에 게시자와 구독자 간에 동기화할 수 있습니다.|  
  
## <a name="options"></a>옵션  
 **구독자 변경 내용 복제**  
 업데이트할 수 있어야 하는 각 구독자에 대한 **복제** 열에서 확인란을 선택합니다. **게시자에서 커밋** 열의 드롭다운 목록 상자에서 업데이트할 수 있는 구독자에 대한 적절한 옵션을 선택합니다.  
  
-   즉시 업데이트 구독에 대해 **동시에 변경 내용 커밋** 을 선택합니다.  
  
-   지연 업데이트 구독에 대해 **변경 내용 대기 및 가능 시 커밋** 을 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Create a Pull Subscription](../../relational-databases/replication/create-a-pull-subscription.md)   
 [ssSDSFull](../../relational-databases/replication/create-a-push-subscription.md)   
 [Subscribe to Publications](../../relational-databases/replication/subscribe-to-publications.md)   
 [Updatable Subscriptions for Transactional Replication](../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
