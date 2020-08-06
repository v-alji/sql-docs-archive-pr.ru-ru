---
title: Использование компонента Database Mail вместо службы SQL Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657700"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="a7623-102">Использование компонента Database Mail вместо службы SQL Mail</span><span class="sxs-lookup"><span data-stu-id="a7623-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="a7623-103">Это правило проверяет представление каталога sys.configurations, чтобы определить, включен ли серверный параметр конфигурации SQL Mail XPs (значение ON).</span><span class="sxs-lookup"><span data-stu-id="a7623-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a7623-104">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="a7623-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a7623-105">Служба SQL Mail будет исключена из будущей версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7623-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a7623-106">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="a7623-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="a7623-107">Чтобы отправить почту, используйте компонент Database Mail.</span><span class="sxs-lookup"><span data-stu-id="a7623-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="a7623-108">Компонент SQL Mail выполняется внутри службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7623-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="a7623-109">При сбое службы SQL Mail сервер также выходит из строя.</span><span class="sxs-lookup"><span data-stu-id="a7623-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="a7623-110">Компонент Database Mail выполняется вне [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в отдельном процессе. Он является масштабируемым и не требует установки клиентских компонентов Extended MAPI на рабочем сервере.</span><span class="sxs-lookup"><span data-stu-id="a7623-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="a7623-111">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="a7623-111">For More Information</span></span>  
 [<span data-ttu-id="a7623-112">Database Mail</span><span class="sxs-lookup"><span data-stu-id="a7623-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7623-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7623-113">See Also</span></span>  
 [<span data-ttu-id="a7623-114">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a7623-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
