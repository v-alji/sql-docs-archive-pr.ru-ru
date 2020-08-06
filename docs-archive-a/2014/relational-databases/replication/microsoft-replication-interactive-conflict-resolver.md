---
title: Интерактивный сопоставитель конфликтов репликации (Майкрософт) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750743"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="120af-102">Интерактивный сопоставитель конфликтов репликации (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="120af-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="120af-103">Интерактивный сопоставитель конфликтов может применяться для подписок на публикации слиянием, которые синхронизируются с помощью диспетчера синхронизации Windows.</span><span class="sxs-lookup"><span data-stu-id="120af-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="120af-104">Он позволяет просматривать, сравнивать, редактировать и выбирать результаты для конфликтов данных.</span><span class="sxs-lookup"><span data-stu-id="120af-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="120af-105">Репликация также содержит средство просмотра конфликтов, позволяющее просматривать и изменять результаты конфликта после их фиксации.</span><span class="sxs-lookup"><span data-stu-id="120af-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="120af-106">Интерактивный сопоставитель конфликтов позволяет выбирать результаты во время выполнения синхронизации.</span><span class="sxs-lookup"><span data-stu-id="120af-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="120af-107">Конфликты, затрагивающие логические записи, не отображаются в интерактивном сопоставителе.</span><span class="sxs-lookup"><span data-stu-id="120af-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="120af-108">Для просмотра сведений о таких конфликтах используются хранимые процедуры репликации.</span><span class="sxs-lookup"><span data-stu-id="120af-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="120af-109">Дополнительные сведения см. в статье [Просмотр сведений о конфликтах для публикаций слиянием &#40;программирование репликации на языке Transact-SQL&#41;](view-conflict-information-for-merge-publications.md).</span><span class="sxs-lookup"><span data-stu-id="120af-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="120af-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="120af-110">Options</span></span>  
 <span data-ttu-id="120af-111">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="120af-111">**Column name**</span></span>  
 <span data-ttu-id="120af-112">Имена всех столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="120af-112">The name of all columns in the table.</span></span> <span data-ttu-id="120af-113">Один или несколько столбцов могли содержать конфликтующие данные.</span><span class="sxs-lookup"><span data-stu-id="120af-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="120af-114">Независимо от того, какие столбцы конфликтуют, вся строка, в пользу которой был разрешен конфликт, переписывает всю проигравшую строку.</span><span class="sxs-lookup"><span data-stu-id="120af-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="120af-115">**Предлагаемое разрешение**</span><span class="sxs-lookup"><span data-stu-id="120af-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="120af-116">Сопоставитель конфликтов предлагает разрешение для статьи.</span><span class="sxs-lookup"><span data-stu-id="120af-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="120af-117">**Издатель**</span><span class="sxs-lookup"><span data-stu-id="120af-117">**Publisher**</span></span>  
 <span data-ttu-id="120af-118">Значение данных на издателе.</span><span class="sxs-lookup"><span data-stu-id="120af-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="120af-119">**Подписчик**</span><span class="sxs-lookup"><span data-stu-id="120af-119">**Subscriber**</span></span>  
 <span data-ttu-id="120af-120">Значение данных на подписчике.</span><span class="sxs-lookup"><span data-stu-id="120af-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="120af-121">**Принять предлагаемый вариант**, **Принять вариант издателя**и **Принять вариант подписчика**</span><span class="sxs-lookup"><span data-stu-id="120af-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="120af-122">Щелкните, чтобы принять строку, которая будет применена на издателе или подписчике, в зависимости от того, в пользу какого участника был разрешен конфликт.</span><span class="sxs-lookup"><span data-stu-id="120af-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="120af-123">Если конфликт был разрешен в пользу подписчика, все другие подписчики получат победившую в конфликте строку при следующей их синхронизации с издателем.</span><span class="sxs-lookup"><span data-stu-id="120af-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="120af-124">**Разрешить оставшиеся конфликты автоматически**</span><span class="sxs-lookup"><span data-stu-id="120af-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="120af-125">Автоматическое разрешение оставшихся конфликтов с помощью предлагаемого разрешения, предоставляемого для статьи сопоставителем конфликтов.</span><span class="sxs-lookup"><span data-stu-id="120af-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="120af-126">**Регистрация подробностей конфликта для последующего обращения**</span><span class="sxs-lookup"><span data-stu-id="120af-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="120af-127">Регистрация подробностей конфликта в системные таблицы.</span><span class="sxs-lookup"><span data-stu-id="120af-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120af-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="120af-128">See Also</span></span>  
 <span data-ttu-id="120af-129">[Интерактивное разрешение конфликтов](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="120af-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="120af-130">[Просмотр и разрешение конфликтов данных для публикации слиянием (SQL Server Management Studio)](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="120af-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="120af-131">[Синхронизация подписки с помощью диспетчера синхронизации Windows (Windows Synchronization Manager)](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="120af-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="120af-132">Advanced Merge Replication Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="120af-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
