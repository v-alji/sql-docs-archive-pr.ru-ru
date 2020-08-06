---
title: MSSQL_ENG020574 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668804"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="fa416-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="fa416-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="fa416-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="fa416-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa416-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="fa416-104">Product Name</span></span>|<span data-ttu-id="fa416-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa416-105">SQL Server</span></span>|  
|<span data-ttu-id="fa416-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="fa416-106">Event ID</span></span>|<span data-ttu-id="fa416-107">20574</span><span class="sxs-lookup"><span data-stu-id="fa416-107">20574</span></span>|  
|<span data-ttu-id="fa416-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="fa416-108">Event Source</span></span>|<span data-ttu-id="fa416-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fa416-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fa416-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="fa416-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="fa416-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="fa416-111">Symbolic Name</span></span>||  
|<span data-ttu-id="fa416-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="fa416-112">Message Text</span></span>|<span data-ttu-id="fa416-113">Ошибка проверки данных подписки подписчика "%s" на статью "%s" в публикации "%s".</span><span class="sxs-lookup"><span data-stu-id="fa416-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa416-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="fa416-114">Explanation</span></span>  
 <span data-ttu-id="fa416-115">Было проверено соответствие данных на подписчике данным на издателе, данные не совпали; таким образом, проверка завершилась неуспешно.</span><span class="sxs-lookup"><span data-stu-id="fa416-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="fa416-116">Дополнительные сведения о проверке см. в разделе [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="fa416-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa416-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="fa416-117">User Action</span></span>  
 <span data-ttu-id="fa416-118">Таким образом, мы рекомендуем сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="fa416-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="fa416-119">Определите причину ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="fa416-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="fa416-120">Исправьте основную проблему, вызвавшую ошибку.</span><span class="sxs-lookup"><span data-stu-id="fa416-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="fa416-121">Устраните конвергенцию данных, повторно инициализировав подписку или применив другой способ.</span><span class="sxs-lookup"><span data-stu-id="fa416-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa416-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa416-122">See Also</span></span>  
 [<span data-ttu-id="fa416-123">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="fa416-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
