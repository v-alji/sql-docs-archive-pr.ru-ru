---
title: Параметры проверки подписки (подписки слиянием) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 458da0387dbaa1b366348c374748c42946893feb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750656"
---
# <a name="subscription-validation-options-merge-subscriptions"></a><span data-ttu-id="e1a81-102">Параметры проверки подписки (подписка на публикацию слиянием)</span><span class="sxs-lookup"><span data-stu-id="e1a81-102">Subscription Validation Options (Merge Subscriptions)</span></span>
  <span data-ttu-id="e1a81-103">Используйте диалоговое окно **Параметры проверки подписки** для указания, нужно ли при проверке использовать только количество строк или количество строк и двоичную контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="e1a81-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1a81-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="e1a81-104">Options</span></span>  
 <span data-ttu-id="e1a81-105">**Проверить только количество строк**</span><span class="sxs-lookup"><span data-stu-id="e1a81-105">**Verify the row counts only**</span></span>  
 <span data-ttu-id="e1a81-106">Выберите этот параметр, чтобы убедиться, что таблица на подписчике имеет то же количество строк, что и таблица на издателе.</span><span class="sxs-lookup"><span data-stu-id="e1a81-106">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="e1a81-107">Этот метод не проверяет соответствие содержимого строк.</span><span class="sxs-lookup"><span data-stu-id="e1a81-107">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="e1a81-108">Проверка количества строк обеспечивает упрощенный подход к проверке, который может уведомить о проблемах с данными.</span><span class="sxs-lookup"><span data-stu-id="e1a81-108">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="e1a81-109">**Проверить количество строк и сравнить контрольные суммы для проверки правильности данных в строке**</span><span class="sxs-lookup"><span data-stu-id="e1a81-109">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="e1a81-110">Кроме подсчета количества строк на подписчике и на издателе, вычисляется контрольная сумма всех данных с помощью двоичного алгоритма подсчета контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="e1a81-110">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="e1a81-111">Если количество строк не совпадает, то контрольная сумма не проверяется.</span><span class="sxs-lookup"><span data-stu-id="e1a81-111">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="e1a81-112">Этот параметр недопустим для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a81-112">This option is not valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a81-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1a81-113">See Also</span></span>  
 <span data-ttu-id="e1a81-114">[Проверка данных на подписчике](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="e1a81-114">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="e1a81-115">Проверка реплицированных данных</span><span class="sxs-lookup"><span data-stu-id="e1a81-115">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
