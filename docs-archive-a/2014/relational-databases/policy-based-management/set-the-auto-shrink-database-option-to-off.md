---
title: Задание значения OFF для параметра базы данных AUTO_SHRINK | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749743"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="6de8b-102">Задание значения параметра базы данных AUTO_SHRINK, равного OFF</span><span class="sxs-lookup"><span data-stu-id="6de8b-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="6de8b-103">Это правило проверяет, имеет ли параметр базы данных AUTO_SHRINK значение OFF.</span><span class="sxs-lookup"><span data-stu-id="6de8b-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="6de8b-104">Нередко сжатие и расширение базы данных ведет к физической фрагментации.</span><span class="sxs-lookup"><span data-stu-id="6de8b-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6de8b-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="6de8b-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="6de8b-106">Присвойте параметру базы данных AUTO_SHRINK значение OFF.</span><span class="sxs-lookup"><span data-stu-id="6de8b-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="6de8b-107">Если известно, что освобождаемое место не понадобится в будущем, можно освободить это место, выполнив сжатие базы данных вручную.</span><span class="sxs-lookup"><span data-stu-id="6de8b-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6de8b-108">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="6de8b-108">For More Information</span></span>  
 <span data-ttu-id="6de8b-109">Статья [315512](https://go.microsoft.com/fwlink/?linkid=117750)базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6de8b-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de8b-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="6de8b-110">See Also</span></span>  
 [<span data-ttu-id="6de8b-111">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="6de8b-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
