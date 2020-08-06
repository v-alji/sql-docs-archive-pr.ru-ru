---
title: Проверка параметра максимального числа рабочих потоков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657698"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="aa5ae-102">Проверка параметра максимального числа рабочих потоков</span><span class="sxs-lookup"><span data-stu-id="aa5ae-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="aa5ae-103">Это правило проверяет возможные неверные значения параметра сервера «max worker threads».</span><span class="sxs-lookup"><span data-stu-id="aa5ae-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="aa5ae-104">Установка низкого значения параметра «max worker threads» может привести к так называемой «нехватке потоков», необходимых для своевременного обслуживания входящих клиентских запросов.</span><span class="sxs-lookup"><span data-stu-id="aa5ae-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="aa5ae-105">Однако слишком большое значение может вызвать неэффективное расходование адресного пространства, поскольку каждому активному потоку требуется 512 КБ на 32-разрядном сервере и до 4 МБ на 64-разрядном сервере.</span><span class="sxs-lookup"><span data-stu-id="aa5ae-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="aa5ae-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="aa5ae-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="aa5ae-107">Выберите для параметра NIB max worker threads значение 0.</span><span class="sxs-lookup"><span data-stu-id="aa5ae-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="aa5ae-108">Это позволит [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически определить нужное число активных рабочих потоков для пользовательских запросов.</span><span class="sxs-lookup"><span data-stu-id="aa5ae-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="aa5ae-109">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="aa5ae-109">For More Information</span></span>  
 [<span data-ttu-id="aa5ae-110">Настройка параметра конфигурации сервера max worker threads</span><span class="sxs-lookup"><span data-stu-id="aa5ae-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa5ae-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa5ae-111">See Also</span></span>  
 [<span data-ttu-id="aa5ae-112">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="aa5ae-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
