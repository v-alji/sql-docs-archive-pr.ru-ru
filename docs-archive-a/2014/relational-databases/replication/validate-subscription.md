---
title: Проверка подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657632"
---
# <a name="validate-subscription"></a><span data-ttu-id="02921-102">Проверка подписки</span><span class="sxs-lookup"><span data-stu-id="02921-102">Validate Subscription</span></span>
  <span data-ttu-id="02921-103">Используйте диалоговое окно **Проверка подписки** , чтобы установить, что подписка на публикацию слиянием должна быть проверена при следующем запуске агента слияния для этой подписки.</span><span class="sxs-lookup"><span data-stu-id="02921-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="02921-104">Результаты подтверждения отображаются в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="02921-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="02921-105">Дополнительные сведения см. в разделе [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="02921-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="02921-106">Кроме того, проверить все подписки на публикацию слиянием можно, щелкнув правой кнопкой мыши публикацию в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и выбрав пункт **Проверить все подписки**.</span><span class="sxs-lookup"><span data-stu-id="02921-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="02921-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="02921-107">Options</span></span>  
 <span data-ttu-id="02921-108">**Дата последней попытки проверки**</span><span class="sxs-lookup"><span data-stu-id="02921-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="02921-109">Дата последнего сеанса работы агента слияния, в ходе которого производилась проверка подписки, независимо от успешности этой проверки.</span><span class="sxs-lookup"><span data-stu-id="02921-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="02921-110">**Дата последней успешной проверки**</span><span class="sxs-lookup"><span data-stu-id="02921-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="02921-111">Дата последнего сеанса работы агента слияния, в ходе которого была произведена успешная проверка подписки.</span><span class="sxs-lookup"><span data-stu-id="02921-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="02921-112">**Проверить эту подписку**</span><span class="sxs-lookup"><span data-stu-id="02921-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="02921-113">Выберите, чтобы проверить подписку.</span><span class="sxs-lookup"><span data-stu-id="02921-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="02921-114">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="02921-114">**Options**</span></span>  
 <span data-ttu-id="02921-115">Нажмите, чтобы получить доступ к диалоговому окну **Параметры проверки подписки** , которое позволит указать, следует ли использовать проверку по количеству строк или по двоичной контрольной сумме.</span><span class="sxs-lookup"><span data-stu-id="02921-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02921-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="02921-116">See Also</span></span>  
 [<span data-ttu-id="02921-117">Проверка реплицированных данных</span><span class="sxs-lookup"><span data-stu-id="02921-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
