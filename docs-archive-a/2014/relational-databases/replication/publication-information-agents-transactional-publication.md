---
title: Сведения о публикации, вкладка "Агенты" (публикация транзакций) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655056"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="340d6-102">Сведения о публикации, агенты (публикация транзакций)</span><span class="sxs-lookup"><span data-stu-id="340d6-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="340d6-103">На вкладке **Агенты** отображаются общие сведения об агентах для выбранной публикации.</span><span class="sxs-lookup"><span data-stu-id="340d6-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="340d6-104">Сведения об агенте моментальных снимков и агенте чтения журнала выводятся для всех публикаций транзакций.</span><span class="sxs-lookup"><span data-stu-id="340d6-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="340d6-105">Сведения об агенте чтения очереди отображается только для тех публикаций транзакций, которые включены для очереди обновляемых подписок.</span><span class="sxs-lookup"><span data-stu-id="340d6-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="340d6-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="340d6-106">Options</span></span>  
 <span data-ttu-id="340d6-107">Чтобы получить дополнительные сведения и задачи, связанные с агентом, щелкните правой кнопкой мыши строку агента и в контекстном меню выберите нужный пункт</span><span class="sxs-lookup"><span data-stu-id="340d6-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="340d6-108">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="340d6-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="340d6-109">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="340d6-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="340d6-110">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="340d6-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="340d6-111">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="340d6-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="340d6-112">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="340d6-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="340d6-113">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="340d6-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="340d6-114">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="340d6-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="340d6-115">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="340d6-115">**Status**</span></span>  
 <span data-ttu-id="340d6-116">Состояние каждого агента репликации, связанного с публикацией.</span><span class="sxs-lookup"><span data-stu-id="340d6-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="340d6-117">Возможные значения состояния показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="340d6-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="340d6-118">Ошибка</span><span class="sxs-lookup"><span data-stu-id="340d6-118">Error</span></span>  
  
-   <span data-ttu-id="340d6-119">Попытка повторно выполнить неудачно завершившиеся команды</span><span class="sxs-lookup"><span data-stu-id="340d6-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="340d6-120">Не выполняется</span><span class="sxs-lookup"><span data-stu-id="340d6-120">Not running</span></span>  
  
-   <span data-ttu-id="340d6-121">Запущен</span><span class="sxs-lookup"><span data-stu-id="340d6-121">Running</span></span>  
  
-   <span data-ttu-id="340d6-122">Завершено</span><span class="sxs-lookup"><span data-stu-id="340d6-122">Completed</span></span>  
  
 <span data-ttu-id="340d6-123">**Агент**</span><span class="sxs-lookup"><span data-stu-id="340d6-123">**Agent**</span></span>  
 <span data-ttu-id="340d6-124">Имя каждого агента репликации, связанного с публикацией.</span><span class="sxs-lookup"><span data-stu-id="340d6-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="340d6-125">Агент распространителя связан с подписками на эту публикацию.</span><span class="sxs-lookup"><span data-stu-id="340d6-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="340d6-126">Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="340d6-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="340d6-127">**Время последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="340d6-127">**Last Start Time**</span></span>  
 <span data-ttu-id="340d6-128">Время последнего запуска агента.</span><span class="sxs-lookup"><span data-stu-id="340d6-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="340d6-129">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="340d6-129">**Duration**</span></span>  
 <span data-ttu-id="340d6-130">Продолжительность выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="340d6-130">The amount of time the agent has run.</span></span> <span data-ttu-id="340d6-131">Этот параметр представляет собой время, прошедшее с момента начала сеанса, если агент запущен в данный момент, или общее время, если агент был запущен ранее.</span><span class="sxs-lookup"><span data-stu-id="340d6-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="340d6-132">**Последнее действие**</span><span class="sxs-lookup"><span data-stu-id="340d6-132">**Last Action**</span></span>  
 <span data-ttu-id="340d6-133">Последнее действие выполнено во время самого последнего выполнения агента.</span><span class="sxs-lookup"><span data-stu-id="340d6-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340d6-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="340d6-134">See Also</span></span>  
 <span data-ttu-id="340d6-135">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="340d6-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="340d6-136">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="340d6-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="340d6-137">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="340d6-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
