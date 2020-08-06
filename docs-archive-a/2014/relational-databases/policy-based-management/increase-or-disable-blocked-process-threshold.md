---
title: Увеличение или отключение порога заблокированных процессов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655693"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="a2177-102">Увеличение или отключение порога заблокированных процессов</span><span class="sxs-lookup"><span data-stu-id="a2177-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="a2177-103">Это правило проверяет, имеет ли параметр «blocked process threshold» значение 0 (отключен) или значение, большее или равное 5 (секундам).</span><span class="sxs-lookup"><span data-stu-id="a2177-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="a2177-104">Присвоение параметру «blocked process threshold» значения от 1 до 4 может привести к постоянной работе монитора взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="a2177-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="a2177-105">Эти значения следует использовать только для устранения неполадок. Их нельзя устанавливать на долгое время или в рабочей среде без участия представителей службы поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2177-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a2177-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="a2177-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a2177-107">Чтобы решить эту проблему, присвойте параметру «blocked process threshold» значение 5 (секунд) или больше либо отключите порог блокировки процессов, присвоив этому параметру значение 0.</span><span class="sxs-lookup"><span data-stu-id="a2177-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="a2177-108">Чтобы присвоить параметру «blocked process threshold» значение `5` секунд, выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="a2177-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="a2177-109">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="a2177-109">For More Information</span></span>  
 [<span data-ttu-id="a2177-110">Параметр конфигурации сервера «blocked process threshold»</span><span class="sxs-lookup"><span data-stu-id="a2177-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="a2177-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2177-111">See Also</span></span>  
 [<span data-ttu-id="a2177-112">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a2177-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
