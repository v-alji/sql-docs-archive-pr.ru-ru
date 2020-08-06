---
title: Свойства заданий (Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732346"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="e82ca-102">Свойства задания (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e82ca-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="e82ca-103">На странице **Свойства задания** можно просматривать сведения о выполняющихся отчетах и подписках перед их отменой.</span><span class="sxs-lookup"><span data-stu-id="e82ca-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="e82ca-104">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов и откройте папку **Задания** .</span><span class="sxs-lookup"><span data-stu-id="e82ca-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="e82ca-105">Щелкните выполняющееся задание правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e82ca-106">Эта функция не поддерживается в [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="e82ca-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="e82ca-107">Эта страница не отображается при запуске выпуска [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e82ca-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e82ca-108">Задания</span><span class="sxs-lookup"><span data-stu-id="e82ca-108">Tasks</span></span>  
 <span data-ttu-id="e82ca-109">Прежде чем сведения о задании можно будет просмотреть, обновите страницу, чтобы получить сведения о заданиях, выполняемых в данный момент на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e82ca-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="e82ca-110">Откройте папку сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="e82ca-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="e82ca-111">Щелкните правой кнопкой мыши **Задания**и выберите команду **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="e82ca-112">Если задание присутствует в списке, щелкните его правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e82ca-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="e82ca-113">Options</span></span>  
 <span data-ttu-id="e82ca-114">**Идентификатор задания**</span><span class="sxs-lookup"><span data-stu-id="e82ca-114">**Job ID**</span></span>  
 <span data-ttu-id="e82ca-115">Идентификатор GUID, присваиваемый заданию во время его обработки.</span><span class="sxs-lookup"><span data-stu-id="e82ca-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="e82ca-116">Это значение формируется случайным образом при каждом запуске отчета или подписки.</span><span class="sxs-lookup"><span data-stu-id="e82ca-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="e82ca-117">**Состояние задания**</span><span class="sxs-lookup"><span data-stu-id="e82ca-117">**Job Status**</span></span>  
 <span data-ttu-id="e82ca-118">Допустимы следующие значения: **Новое** и **Выполняется**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="e82ca-119">В начале выполнения задание всегда имеет состояние **Новое** .</span><span class="sxs-lookup"><span data-stu-id="e82ca-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="e82ca-120">Через 60 секунд состояние меняется на **Выполняется**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="e82ca-121">Чтобы отобразить это изменение, необходимо обновить страницу.</span><span class="sxs-lookup"><span data-stu-id="e82ca-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="e82ca-122">**Тип задания**</span><span class="sxs-lookup"><span data-stu-id="e82ca-122">**Job Type**</span></span>  
 <span data-ttu-id="e82ca-123">Допустимы следующие значения: **Пользовательское** и **Системное**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="e82ca-124">Пользовательским заданием является любое задание, инициированное отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="e82ca-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="e82ca-125">Сюда входит запуск отчета по требованию, формирование моментального снимка журнала отчета или создание снимка состояния выполнения отчета вручную.</span><span class="sxs-lookup"><span data-stu-id="e82ca-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="e82ca-126">Выполняющаяся обычная подписка также является пользовательским заданием.</span><span class="sxs-lookup"><span data-stu-id="e82ca-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="e82ca-127">Системным заданием является задание, инициируемое сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="e82ca-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="e82ca-128">К системным заданиям относится и обработка отчетов, запускаемая по расписанию.</span><span class="sxs-lookup"><span data-stu-id="e82ca-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="e82ca-129">**Действие задания**</span><span class="sxs-lookup"><span data-stu-id="e82ca-129">**Job Action**</span></span>  
 <span data-ttu-id="e82ca-130">Для отчетов в этом столбце показываются процессы выполнения, которые в настоящее время работают.</span><span class="sxs-lookup"><span data-stu-id="e82ca-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="e82ca-131">Всегда принимает значение **Подготовка отчетов**.</span><span class="sxs-lookup"><span data-stu-id="e82ca-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="e82ca-132">**Описание задания**</span><span class="sxs-lookup"><span data-stu-id="e82ca-132">**Job Description**</span></span>  
 <span data-ttu-id="e82ca-133">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] по умолчанию не обеспечивает описание заданий.</span><span class="sxs-lookup"><span data-stu-id="e82ca-133">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="e82ca-134">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="e82ca-134">**Server Name**</span></span>  
 <span data-ttu-id="e82ca-135">Показывает имя сервера отчетов, на котором выполняется обработка задания.</span><span class="sxs-lookup"><span data-stu-id="e82ca-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="e82ca-136">Если было настроено масштабное развертывание, это значение показывает, какой из серверов обрабатывает задание.</span><span class="sxs-lookup"><span data-stu-id="e82ca-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="e82ca-137">**Имя отчета**</span><span class="sxs-lookup"><span data-stu-id="e82ca-137">**Report Name**</span></span>  
 <span data-ttu-id="e82ca-138">Отображается имя отчета.</span><span class="sxs-lookup"><span data-stu-id="e82ca-138">Shows the name of the report.</span></span> <span data-ttu-id="e82ca-139">Подписки идентифицируются описаниями.</span><span class="sxs-lookup"><span data-stu-id="e82ca-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="e82ca-140">**Путь отчета**</span><span class="sxs-lookup"><span data-stu-id="e82ca-140">**Report Path**</span></span>  
 <span data-ttu-id="e82ca-141">Показывает путь к отчету в иерархии папок на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e82ca-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="e82ca-142">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="e82ca-142">**Start Time**</span></span>  
 <span data-ttu-id="e82ca-143">Указывается время запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="e82ca-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="e82ca-144">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="e82ca-144">**User Name**</span></span>  
 <span data-ttu-id="e82ca-145">Для процессов, инициируемых пользователем, в этом столбце отображается имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e82ca-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="e82ca-146">Для системных заданий отображается имя сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="e82ca-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82ca-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="e82ca-147">See Also</span></span>  
 <span data-ttu-id="e82ca-148">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e82ca-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="e82ca-149">[Подключение к серверу отчетов в среде Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="e82ca-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="e82ca-150">Управление запущенным процессом</span><span class="sxs-lookup"><span data-stu-id="e82ca-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
