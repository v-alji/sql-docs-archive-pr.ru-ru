---
title: MSSQL_ENG020572 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668805"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="239ba-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="239ba-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="239ba-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="239ba-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="239ba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="239ba-104">Product Name</span></span>|<span data-ttu-id="239ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="239ba-105">SQL Server</span></span>|  
|<span data-ttu-id="239ba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="239ba-106">Event ID</span></span>|<span data-ttu-id="239ba-107">20572</span><span class="sxs-lookup"><span data-stu-id="239ba-107">20572</span></span>|  
|<span data-ttu-id="239ba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="239ba-108">Event Source</span></span>|<span data-ttu-id="239ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="239ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="239ba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="239ba-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="239ba-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="239ba-111">Symbolic Name</span></span>||  
|<span data-ttu-id="239ba-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="239ba-112">Message Text</span></span>|<span data-ttu-id="239ba-113">Подписка подписчика "%s" на статью "%s" в публикации "%s" повторно инициализирована после ошибки при проверке.</span><span class="sxs-lookup"><span data-stu-id="239ba-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="239ba-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="239ba-114">Explanation</span></span>  
 <span data-ttu-id="239ba-115">Было проверено соответствие данных на подписчике данным на издателе, данные не совпали; таким образом, проверка завершилась неуспешно.</span><span class="sxs-lookup"><span data-stu-id="239ba-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="239ba-116">При включении проверки был выбран параметр, указывающий, что в случае ошибки проверки подписка должна быть повторно инициализирована.</span><span class="sxs-lookup"><span data-stu-id="239ba-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="239ba-117">Повторная инициализация подписки включает применение нового моментального снимка на подписчике.</span><span class="sxs-lookup"><span data-stu-id="239ba-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="239ba-118">Дополнительные сведения о проверке см. в разделе [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="239ba-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="239ba-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="239ba-119">User Action</span></span>  
 <span data-ttu-id="239ba-120">После применения нового моментального снимка на подписчике данные на издателе и подписчике будут соответствовать друг другу.</span><span class="sxs-lookup"><span data-stu-id="239ba-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239ba-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="239ba-121">See Also</span></span>  
 [<span data-ttu-id="239ba-122">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="239ba-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
