---
title: Домены приложений и безопасность интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657262"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="bff5f-102">Домены приложений и безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="bff5f-102">Application Domains and CLR Integration Security</span></span>
  <span data-ttu-id="bff5f-103">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сборки, принадлежащие одному и тому же владельцу, загружаются в одном и том же домене приложений.</span><span class="sxs-lookup"><span data-stu-id="bff5f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="bff5f-104">Благодаря тому, что весь набор сборок работает в одном и том же домене приложений, сборки могут обнаруживать друг друга во время выполнения с помощью API-интерфейсов отражения платформы .NET Framework или других средств, а также могут выполнять взаимные вызовы в режиме позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="bff5f-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="bff5f-105">Такие вызовы выполняются по отношению к сборкам, принадлежащим одному и тому же владельцу, поэтому для этих вызовов не проверяются разрешения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bff5f-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="bff5f-106">Указанная схема размещения сборок в доменах приложений предназначена главным образом для обеспечения масштабируемости, безопасности и взаимной изоляции и может измениться в будущих версиях.</span><span class="sxs-lookup"><span data-stu-id="bff5f-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="bff5f-107">Поэтому не следует рассчитывать на то, что всегда можно будет осуществлять поиск сборок в одном и том же домене приложений с помощью механизмов позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="bff5f-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff5f-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="bff5f-108">See Also</span></span>  
 [<span data-ttu-id="bff5f-109">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="bff5f-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
