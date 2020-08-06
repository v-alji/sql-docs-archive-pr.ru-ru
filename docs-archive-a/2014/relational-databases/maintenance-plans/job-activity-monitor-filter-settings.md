---
title: Монитор активности заданий (настройки фильтра) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.filter.f1
ms.assetid: 89cb0055-5262-447f-8464-7203d4caba78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feba7b992d5d1d375b93df12135487a092792ee1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666570"
---
# <a name="job-activity-monitor-filter-settings"></a><span data-ttu-id="d3a46-102">Монитор активности заданий (настройки фильтра)</span><span class="sxs-lookup"><span data-stu-id="d3a46-102">Job Activity Monitor (Filter Settings)</span></span>
  <span data-ttu-id="d3a46-103">Эта страница используется для уменьшения числа строк, видимых в мониторе активности заданий.</span><span class="sxs-lookup"><span data-stu-id="d3a46-103">Use this page to reduce the number of rows visible in the Job Activity Monitor.</span></span> <span data-ttu-id="d3a46-104">Введите критерии в одно или несколько из доступных полей для отображения только строк, удовлетворяющих заданным условиям.</span><span class="sxs-lookup"><span data-stu-id="d3a46-104">Enter criteria in one or several of the available boxes, to show only the rows that meet the specified values.</span></span> <span data-ttu-id="d3a46-105">Для некоторых полей, например **Состояние** или **Тип блокировки** , имеется ограниченное количество возможных значений, представленных в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="d3a46-105">Some of the boxes, such as **Status** or **Blocking Type** offer a finite number of possible values, provided by a drop-down list.</span></span> <span data-ttu-id="d3a46-106">Другие, например **Приложение** , позволяют вводить не только любое значение, но и любое их количество в виде списка, разделенного запятыми.</span><span class="sxs-lookup"><span data-stu-id="d3a46-106">Others, such as **Application,** allow you to enter whatever value and as many values as you wish, as a comma separated list.</span></span> <span data-ttu-id="d3a46-107">Значки панели инструментов позволяют сортировать доступные поля по категориям или в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="d3a46-107">Toolbar icons allow you to sort the available boxes by category or alphabetically.</span></span> <span data-ttu-id="d3a46-108">Щелкните каждый из критериев для просмотра краткого его описания.</span><span class="sxs-lookup"><span data-stu-id="d3a46-108">Click the criteria to show a short description of the each one.</span></span>  
  
 <span data-ttu-id="d3a46-109">Для осуществления фильтрации в мониторе активности заданий укажите столько критериев фильтрации, сколько необходимо, щелкните **Применить фильтр**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3a46-109">To filter the Job Activity Monitor, provide as many filter criteria as you want, click **Apply filter**, and then click **OK**.</span></span>  
  
## <a name="all-jobs"></a><span data-ttu-id="d3a46-110">Все задания</span><span class="sxs-lookup"><span data-stu-id="d3a46-110">All Jobs</span></span>  
 <span data-ttu-id="d3a46-111">Эта группа критериев доступна для фильтрации в мониторе активности заданий.</span><span class="sxs-lookup"><span data-stu-id="d3a46-111">This group of filter criteria is available when filtering the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="d3a46-112">**Название**</span><span class="sxs-lookup"><span data-stu-id="d3a46-112">**Name**</span></span>  
 <span data-ttu-id="d3a46-113">Фильтрация заданий по имени.</span><span class="sxs-lookup"><span data-stu-id="d3a46-113">Filter jobs by name.</span></span>  
  
 <span data-ttu-id="d3a46-114">**Следующий запуск**</span><span class="sxs-lookup"><span data-stu-id="d3a46-114">**Next Run**</span></span>  
 <span data-ttu-id="d3a46-115">Фильтрация по дате следующего назначенного запуска.</span><span class="sxs-lookup"><span data-stu-id="d3a46-115">Filter by the date next scheduled to run.</span></span>  
  
 <span data-ttu-id="d3a46-116">**Готово к запуску**</span><span class="sxs-lookup"><span data-stu-id="d3a46-116">**Runnable**</span></span>  
 <span data-ttu-id="d3a46-117">Просмотр заданий, которые могут быть запущены или которые не могут быть запущены.</span><span class="sxs-lookup"><span data-stu-id="d3a46-117">View jobs that can be run, or jobs that cannot be run.</span></span> <span data-ttu-id="d3a46-118">Выберите **Да** , чтобы посмотреть только те задания, которые могут быть запущены; или выберите **Нет** , чтобы посмотреть только те задания, которые не могут быть запущены; либо выберите **Все** , чтобы посмотреть все задания.</span><span class="sxs-lookup"><span data-stu-id="d3a46-118">Select **Yes** to view only jobs that can be run, select **No** to view only jobs that cannot be run, or select **All** to view both jobs that can be run and those that cannot.</span></span>  
  
 <span data-ttu-id="d3a46-119">**Последний запуск**</span><span class="sxs-lookup"><span data-stu-id="d3a46-119">**Last Run**</span></span>  
 <span data-ttu-id="d3a46-120">Фильтрация по дате последнего запуска.</span><span class="sxs-lookup"><span data-stu-id="d3a46-120">Filter by the date last run.</span></span>  
  
 <span data-ttu-id="d3a46-121">**Результат последнего запуска**</span><span class="sxs-lookup"><span data-stu-id="d3a46-121">**Last Run Outcome**</span></span>  
 <span data-ttu-id="d3a46-122">Фильтрация заданий по состоянию последнего их запуска.</span><span class="sxs-lookup"><span data-stu-id="d3a46-122">Filter jobs by the status last time the jobs were run.</span></span>  
  
 <span data-ttu-id="d3a46-123">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="d3a46-123">**Enabled**</span></span>  
 <span data-ttu-id="d3a46-124">Просмотр только включенных или отключенных заданий</span><span class="sxs-lookup"><span data-stu-id="d3a46-124">View only enabled or not enabled jobs</span></span>  
  
 <span data-ttu-id="d3a46-125">**Категория**</span><span class="sxs-lookup"><span data-stu-id="d3a46-125">**Category**</span></span>  
 <span data-ttu-id="d3a46-126">Фильтрация заданий по категории задания.</span><span class="sxs-lookup"><span data-stu-id="d3a46-126">Filter jobs by the job category.</span></span>  
  
 <span data-ttu-id="d3a46-127">**Назначено**</span><span class="sxs-lookup"><span data-stu-id="d3a46-127">**Scheduled**</span></span>  
 <span data-ttu-id="d3a46-128">Просмотр назначенных или неназначенных заданий по расписанию.</span><span class="sxs-lookup"><span data-stu-id="d3a46-128">View all jobs with schedules, or without schedules.</span></span>  
  
 <span data-ttu-id="d3a46-129">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d3a46-129">**Status**</span></span>  
 <span data-ttu-id="d3a46-130">Фильтрация заданий по состоянию.</span><span class="sxs-lookup"><span data-stu-id="d3a46-130">Filter jobs by the status.</span></span>  
  
## <a name="description-area"></a><span data-ttu-id="d3a46-131">Область описания</span><span class="sxs-lookup"><span data-stu-id="d3a46-131">Description Area</span></span>  
 <span data-ttu-id="d3a46-132">**Окно описания**</span><span class="sxs-lookup"><span data-stu-id="d3a46-132">**Description Box**</span></span>  
 <span data-ttu-id="d3a46-133">В этом неименованном окне выводится краткое описание критериев по мере их выделения.</span><span class="sxs-lookup"><span data-stu-id="d3a46-133">This unnamed box provides a short description of the criteria as they are selected.</span></span>  
  
 <span data-ttu-id="d3a46-134">**Применить фильтр**</span><span class="sxs-lookup"><span data-stu-id="d3a46-134">**Apply filter**</span></span>  
 <span data-ttu-id="d3a46-135">Чтобы применить фильтр, нажмите кнопку **Применить фильтр** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3a46-135">To apply the filter, click **Apply filter** and then click **OK**.</span></span> <span data-ttu-id="d3a46-136">Чтобы сохранить параметры фильтра в диалоговом окне **Параметры фильтра** , но не применять их, снимите флажок **Применить фильтр**и нажмите кнопку **ОК**, чтобы отобразить все строки.</span><span class="sxs-lookup"><span data-stu-id="d3a46-136">To retain the filter settings in the **Filter Settings** dialog box, but not apply them, uncheck **Apply filter**, and then click **OK**, to display all rows.</span></span>  
  
 <span data-ttu-id="d3a46-137">**Clear**</span><span class="sxs-lookup"><span data-stu-id="d3a46-137">**Clear**</span></span>  
 <span data-ttu-id="d3a46-138">Позволяет вернуть настройки фильтра к установленным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3a46-138">Returns the filter settings back to the default settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a46-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3a46-139">See Also</span></span>  
 [<span data-ttu-id="d3a46-140">Наблюдение за активностью заданий</span><span class="sxs-lookup"><span data-stu-id="d3a46-140">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
