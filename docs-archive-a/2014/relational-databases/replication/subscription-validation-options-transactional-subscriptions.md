---
title: Параметры проверки подписки (транзакционные подписки) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750652"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="bf770-102">Параметры проверки подписки (подписки на публикацию транзакций)</span><span class="sxs-lookup"><span data-stu-id="bf770-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="bf770-103">Используйте диалоговое окно **Параметры проверки подписки** , чтобы указать, должна ли проверка использовать только количество строк или число строк и двоичная контрольная сумма.</span><span class="sxs-lookup"><span data-stu-id="bf770-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf770-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="bf770-104">Options</span></span>  
 <span data-ttu-id="bf770-105">**Проверить, совпадают ли числа реплицированных строк данных у подписчика и у издателя**</span><span class="sxs-lookup"><span data-stu-id="bf770-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="bf770-106">Выберите для выполнения тип проверки количества строк.</span><span class="sxs-lookup"><span data-stu-id="bf770-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="bf770-107">Для публикаций Oracle единственный доступный параметр — это параметр **Выполнить подсчет действительного числа строк путем непосредственных запросов к таблицам**.</span><span class="sxs-lookup"><span data-stu-id="bf770-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="bf770-108">**Сравнить контрольные суммы для проверки правильности данных в строке**</span><span class="sxs-lookup"><span data-stu-id="bf770-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="bf770-109">Кроме подсчета количества строк на подписчике и на издателе, вычисляется контрольная сумма всех данных с помощью двоичного алгоритма подсчета контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="bf770-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="bf770-110">Если количество строк не совпадает, то контрольная сумма не проверяется.</span><span class="sxs-lookup"><span data-stu-id="bf770-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="bf770-111">**Остановить агент распространителя после завершения проверки**</span><span class="sxs-lookup"><span data-stu-id="bf770-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="bf770-112">По умолчанию агент распространителя работает постоянно.</span><span class="sxs-lookup"><span data-stu-id="bf770-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="bf770-113">Выберите этот параметр для остановки агента после выполнения проверки.</span><span class="sxs-lookup"><span data-stu-id="bf770-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="bf770-114">Это позволяет удостовериться в успешном завершении проверки перед продолжением копирования данных к подписчику.</span><span class="sxs-lookup"><span data-stu-id="bf770-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf770-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf770-115">See Also</span></span>  
 <span data-ttu-id="bf770-116">[Проверка данных на подписчике](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="bf770-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="bf770-117">Проверка реплицированных данных</span><span class="sxs-lookup"><span data-stu-id="bf770-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
