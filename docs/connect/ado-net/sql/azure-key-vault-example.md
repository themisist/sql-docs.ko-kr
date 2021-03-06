---
title: Always Encrypted에서 Azure Key Vault 공급자 사용을 보여 주는 예제 | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.reviewer: v-kaywon
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: tutorial
author: karinazhou
ms.author: v-jizho2
ms.openlocfilehash: fca498fbc7f79dcfc8852799ade6e230952ea082
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "75250950"
---
# <a name="example-demonstrating-use-of-azure-key-vault-provider-with-always-encrypted"></a>Always Encrypted에서 Azure Key Vault 공급자 사용을 보여 주는 예제

[!INCLUDE [tsql-appliesto-ssver15-xxxx-xxxx-xxx-winonly](../../../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx-winonly.md)]

[!INCLUDE [appliesto-netfx-netcore-xxxx-md](../../../includes/appliesto-netfx-netcore-xxxx-md.md)]

이 예제에서는 암호화된 열에 액세스할 때 Azure Key Vault 공급자를 사용하는 방법을 보여 줍니다.

[!code-csharp [AKVProvider Example#1](~/../sqlclient/doc/samples/AzureKeyVaultProviderExample.cs#1)]

## <a name="see-also"></a>참고 항목

- [보안 Enclave를 사용한 Always Encrypted에서 Azure Key Vault 공급자 사용을 보여 주는 예제](azure-key-vault-enclave-example.md)
- [자습서: 보안 enclave를 사용한 Always Encrypted를 이용하여 .NET 애플리케이션 개발](tutorial-always-encrypted-enclaves-develop-net-apps.md)을 참조하세요.
- [Microsoft .NET Data Provider for SQL Server와 Always Encrypted 사용](sqlclient-support-always-encrypted.md)
