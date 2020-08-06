---
title: Инициализация всех подписок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666483"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="58cb4-102">Проверка всех подписок</span><span class="sxs-lookup"><span data-stu-id="58cb4-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="58cb4-103">Чтобы указать, что все подписки на публикацию слиянием должны быть проверены при следующем запуске агента слияния, для каждой подписки используется диалоговое окно **Проверка всех подписок** .</span><span class="sxs-lookup"><span data-stu-id="58cb4-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="58cb4-104">Результаты подтверждения отображаются в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="58cb4-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="58cb4-105">Дополнительные сведения см. в разделе [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="58cb4-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="58cb4-106">Отдельную подписку можно проверить, щелкнув ее правой кнопкой мыши в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и выбрав пункт **Проверка подписки**.</span><span class="sxs-lookup"><span data-stu-id="58cb4-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="58cb4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="58cb4-107">Options</span></span>  
 <span data-ttu-id="58cb4-108">**Проверить только количество строк**</span><span class="sxs-lookup"><span data-stu-id="58cb4-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="58cb4-109">Выберите этот параметр, чтобы убедиться, что таблица на подписчике имеет то же количество строк, что и таблица на издателе.</span><span class="sxs-lookup"><span data-stu-id="58cb4-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="58cb4-110">Этот метод не проверяет соответствие содержимого строк.</span><span class="sxs-lookup"><span data-stu-id="58cb4-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="58cb4-111">Проверка количества строк обеспечивает упрощенный подход к проверке, который может уведомить о проблемах с данными.</span><span class="sxs-lookup"><span data-stu-id="58cb4-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="58cb4-112">**Проверить количество строк и сравнить контрольные суммы для проверки правильности данных в строке**</span><span class="sxs-lookup"><span data-stu-id="58cb4-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="58cb4-113">Кроме подсчета количества строк на подписчике и на издателе, вычисляется контрольная сумма всех данных с помощью двоичного алгоритма подсчета контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="58cb4-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="58cb4-114">Если количество строк не совпадает, то контрольная сумма не проверяется.</span><span class="sxs-lookup"><span data-stu-id="58cb4-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="58cb4-115">Этот параметр недопустим для [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58cb4-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cb4-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="58cb4-116">See Also</span></span>  
 [<span data-ttu-id="58cb4-117">Проверка реплицированных данных</span><span class="sxs-lookup"><span data-stu-id="58cb4-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
