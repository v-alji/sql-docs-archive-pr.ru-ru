---
title: Обнаружение невыполненного входного запроса на выход | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 85373b2e-d9fe-42ef-9653-6e22fe5ecab0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b3cdc219de06592924ca74cad33ed0027963ac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728209"
---
# <a name="detect-failed-input-output-request"></a><span data-ttu-id="ad5ec-102">Обнаружить неудачный входящий запрос на выход</span><span class="sxs-lookup"><span data-stu-id="ad5ec-102">Detect Failed Input Output Request</span></span>
  <span data-ttu-id="ad5ec-103">Это правило проверяет журнал системных событий на наличие события с идентификатором EventId 50.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-103">This rule checks the system event log for EventId 50.</span></span> <span data-ttu-id="ad5ec-104">Ошибка вызвана сбоем запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ad5ec-104">This error is caused by a failed I/O request.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ad5ec-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ad5ec-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ad5ec-106">Дополнительные сведения об устранении этой ошибки см. в следующих статьях базы знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ad5ec-106">Review the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles for more information about how to troubleshoot this error:</span></span>  
  
-   [<span data-ttu-id="ad5ec-107">Статья 311081 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ad5ec-107">Microsoft Knowledge Base article 311081</span></span>](https://go.microsoft.com/fwlink/?linkid=117744)  
  
-   [<span data-ttu-id="ad5ec-108">Статья 885688 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ad5ec-108">Microsoft Knowledge Base article 885688</span></span>](https://go.microsoft.com/fwlink/?linkid=117745)  
  
  
