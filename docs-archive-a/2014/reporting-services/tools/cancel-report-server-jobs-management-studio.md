---
title: Отмена заданий сервера отчетов (Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737910"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="203f0-102">Отмена заданий сервера отчетов (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="203f0-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="203f0-103">Диалоговое окно **Отмена заданий сервера отчетов** позволяет просмотреть или отменить выполняющиеся отчеты.</span><span class="sxs-lookup"><span data-stu-id="203f0-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="203f0-104">В этом диалоговом окне отображаются все задания, выполняемые в данный момент на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="203f0-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="203f0-105">Несмотря на то, что выполняемые задания нельзя приостановить или перезапустить, задачи, завершение которых требует слишком долгого времени, можно отменить — все сразу или по отдельности.</span><span class="sxs-lookup"><span data-stu-id="203f0-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="203f0-106">Отменить можно как пользовательские, так и системные задания.</span><span class="sxs-lookup"><span data-stu-id="203f0-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="203f0-107">Пользовательским заданием является любое задание, инициированное отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="203f0-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="203f0-108">Сюда входит запуск отчета по требованию, создание моментального снимка журнала отчета или создание снимка состояния выполнения отчета вручную.</span><span class="sxs-lookup"><span data-stu-id="203f0-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="203f0-109">Выполняющаяся обычная подписка также является пользовательским заданием.</span><span class="sxs-lookup"><span data-stu-id="203f0-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="203f0-110">Системным заданием является задание, инициируемое сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="203f0-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="203f0-111">К системным заданиям относится плановая обработка отчетов.</span><span class="sxs-lookup"><span data-stu-id="203f0-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="203f0-112">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов, щелкните **Задания**правой кнопкой мыши и выберите команду **Отменить все задания**.</span><span class="sxs-lookup"><span data-stu-id="203f0-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="203f0-113">Можно также открыть **Задания**, щелкнуть задание, выполняемое на сервере отчетов, правой кнопкой мыши и выбрать команду **Отменить задание**.</span><span class="sxs-lookup"><span data-stu-id="203f0-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="203f0-114">Прежде чем отменить какое-либо задание, можно просмотреть его свойства и определить, когда оно было запущено.</span><span class="sxs-lookup"><span data-stu-id="203f0-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="203f0-115">Дополнительные сведения см. в разделе [Свойства задания &#40;Management Studio&#41;](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="203f0-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="203f0-116">Эта функция не поддерживается в [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="203f0-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="203f0-117">Эта страница не отображается при запуске выпуска [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203f0-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="203f0-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="203f0-118">Options</span></span>  
 <span data-ttu-id="203f0-119">**Название**</span><span class="sxs-lookup"><span data-stu-id="203f0-119">**Name**</span></span>  
 <span data-ttu-id="203f0-120">Отображается имя отчета.</span><span class="sxs-lookup"><span data-stu-id="203f0-120">Shows the name of the report.</span></span> <span data-ttu-id="203f0-121">Подписки идентифицируются описаниями.</span><span class="sxs-lookup"><span data-stu-id="203f0-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="203f0-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="203f0-122">**Type**</span></span>  
 <span data-ttu-id="203f0-123">Допустимы следующие значения: **Пользовательское** и **Системное**.</span><span class="sxs-lookup"><span data-stu-id="203f0-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="203f0-124">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="203f0-124">**Start Time**</span></span>  
 <span data-ttu-id="203f0-125">Указывается время запуска задания.</span><span class="sxs-lookup"><span data-stu-id="203f0-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="203f0-126">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="203f0-126">**User Name**</span></span>  
 <span data-ttu-id="203f0-127">Для заданий, запущенных пользователем, в этом столбце отображается имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="203f0-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="203f0-128">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="203f0-128">**Status**</span></span>  
 <span data-ttu-id="203f0-129">Показывается состояние задания.</span><span class="sxs-lookup"><span data-stu-id="203f0-129">Shows the status of the job.</span></span> <span data-ttu-id="203f0-130">Допустимы следующие значения: **Новое** и **Выполняется**.</span><span class="sxs-lookup"><span data-stu-id="203f0-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="203f0-131">В начале выполнения задание всегда имеет состояние **Новое** .</span><span class="sxs-lookup"><span data-stu-id="203f0-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="203f0-132">Через 60 секунд состояние меняется на **Выполняется**.</span><span class="sxs-lookup"><span data-stu-id="203f0-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="203f0-133">Чтобы отобразить это изменение, необходимо обновить страницу.</span><span class="sxs-lookup"><span data-stu-id="203f0-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="203f0-134">**OK**</span><span class="sxs-lookup"><span data-stu-id="203f0-134">**OK**</span></span>  
 <span data-ttu-id="203f0-135">Отменяет отдельное задание или несколько заданий.</span><span class="sxs-lookup"><span data-stu-id="203f0-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="203f0-136">Отмена заданий осуществляется немедленно, и их возобновление невозможно.</span><span class="sxs-lookup"><span data-stu-id="203f0-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="203f0-137">Если отмена задания была выполнена ошибочно, нужно запустить новое задание, повторно отправив запрос на выполнение отчета или подписки.</span><span class="sxs-lookup"><span data-stu-id="203f0-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203f0-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="203f0-138">See Also</span></span>  
 <span data-ttu-id="203f0-139">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="203f0-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="203f0-140">[Подключение к серверу отчетов в среде Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="203f0-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="203f0-141">Управление запущенным процессом</span><span class="sxs-lookup"><span data-stu-id="203f0-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
