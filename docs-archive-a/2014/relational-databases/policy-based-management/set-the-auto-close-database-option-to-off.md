---
title: Задание значения OFF для параметра базы данных AUTO_CLOSE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749744"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="1424b-102">Задание значения OFF для параметра базы данных AUTO_CLOSE</span><span class="sxs-lookup"><span data-stu-id="1424b-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="1424b-103">Это правило проверяет, имеет ли параметр AUTO_ CLOSE значение OFF.</span><span class="sxs-lookup"><span data-stu-id="1424b-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="1424b-104">Если параметр AUTO_CLOSE имеет значение ON, это может привести к снижению производительности баз данных, к которым часто выполняются обращения, из-за увеличения издержек на открытие и закрытие базы данных после каждого соединения.</span><span class="sxs-lookup"><span data-stu-id="1424b-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="1424b-105">Параметр AUTO_CLOSE также очищает кэш процедур после каждого соединения.</span><span class="sxs-lookup"><span data-stu-id="1424b-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="1424b-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1424b-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="1424b-107">При частом обращении к базе данных присвойте параметру AUTO_CLOSE базы данных значение OFF.</span><span class="sxs-lookup"><span data-stu-id="1424b-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="1424b-108">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="1424b-108">For More Information</span></span>  
 [<span data-ttu-id="1424b-109">Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1424b-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="1424b-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="1424b-110">See Also</span></span>  
 [<span data-ttu-id="1424b-111">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="1424b-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
