---
title: Создание сеанса расширенных событий с помощью мастера (обозреватель объектов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664473"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="61225-102">создать сеанс расширенных событий с помощью пользовательского интерфейса нового сеанса (обозреватель объектов)</span><span class="sxs-lookup"><span data-stu-id="61225-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="61225-103">Для повышения удобства выбора и отслеживания событий на сервере в расширенных событиях предусмотрен мастер создания сеансов, который помогает создавать сеансы расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="61225-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="61225-104">Мастер создания сеанса предоставляет доступ к большинству функций для обработки расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="61225-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="61225-105">В диалоговом окне [Создание сеанса](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) также можно задать сеанс расширенных событий, в ходе которого будет выполняться сбор, отображение и анализ данных.</span><span class="sxs-lookup"><span data-stu-id="61225-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="61225-106">Диалоговое окно «Создание сеанса» включает все функции расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="61225-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="61225-107">Открытие мастера новых сеансов</span><span class="sxs-lookup"><span data-stu-id="61225-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="61225-108">В обозревателе объектов разверните узел **Управление** , затем узел **Расширенные события**.</span><span class="sxs-lookup"><span data-stu-id="61225-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="61225-109">Щелкните правой кнопкой мыши **Сеансы**и выберите **Мастер новых сеансов**.</span><span class="sxs-lookup"><span data-stu-id="61225-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="61225-110">Создание сеанса событий с помощью страниц мастера новых сеансов</span><span class="sxs-lookup"><span data-stu-id="61225-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="61225-111">Введение</span><span class="sxs-lookup"><span data-stu-id="61225-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="61225-112">Настройка свойств сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="61225-113">Выбор шаблона</span><span class="sxs-lookup"><span data-stu-id="61225-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="61225-114">Выбор событий для отслеживания</span><span class="sxs-lookup"><span data-stu-id="61225-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="61225-115">Отслеживание глобальных полей</span><span class="sxs-lookup"><span data-stu-id="61225-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="61225-116">Настройка фильтров событий сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="61225-117">Настройка хранилища данных сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="61225-118">Сводка</span><span class="sxs-lookup"><span data-stu-id="61225-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="61225-119">Создание сеанса событий</span><span class="sxs-lookup"><span data-stu-id="61225-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="61225-120">Общие</span><span class="sxs-lookup"><span data-stu-id="61225-120">Introduction</span></span>  
 <span data-ttu-id="61225-121">На странице **Введение** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="61225-122">На странице **Введение** мастера новых сеансов нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="61225-123">Установите флажок **Больше не показывать эту страницу**, если мастер планируется использовать повторно и не требуется читать введение каждый раз при его запуске.</span><span class="sxs-lookup"><span data-stu-id="61225-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="61225-124">Задание свойств сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-124">Set Session Properties</span></span>  
 <span data-ttu-id="61225-125">На странице **Настройка свойств сеанса** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="61225-126">В поле **Имя сеанса** введите понятное имя сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="61225-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="61225-127">Если требуется запускать сеанс при запуске сервера, установите флажок **Запускать сеанс событий при запуске сервера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="61225-128">Выбор шаблона</span><span class="sxs-lookup"><span data-stu-id="61225-128">Choose Template</span></span>  
 <span data-ttu-id="61225-129">На странице **Выбор шаблона** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="61225-130">Выберите параметр **Использовать этот шаблон сеанса событий** , чтобы выбрать один из стандартных шаблонов для типовых проблем.</span><span class="sxs-lookup"><span data-stu-id="61225-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="61225-131">Выберите нужный шаблон в раскрывающемся списке и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="61225-132">-или-</span><span class="sxs-lookup"><span data-stu-id="61225-132">-OR-</span></span>  
  
-   <span data-ttu-id="61225-133">Выберите параметр **Не использовать шаблон** , если не нужно использовать стандартный шаблон, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="61225-134">Выбор событий для захвата</span><span class="sxs-lookup"><span data-stu-id="61225-134">Select Events to Capture</span></span>  
 <span data-ttu-id="61225-135">На странице **Выбор событий для отслеживания** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="61225-136">Выберите события, которые следует отслеживать в поле **Библиотека событий**, затем щелкните стрелку вправо.</span><span class="sxs-lookup"><span data-stu-id="61225-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="61225-137">В разделе «Библиотека событий» можно выбрать несколько событий одновременно с помощью клавиш CTRL и SHIFT.</span><span class="sxs-lookup"><span data-stu-id="61225-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="61225-138">Метод поиска отслеживаемых событий можно выбрать в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="61225-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="61225-139">Например, можно выполнить поиск имен событий или имен событий и их описаний.</span><span class="sxs-lookup"><span data-stu-id="61225-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="61225-140">Поддерживается поиск любых слов в таблице путем ввода текста для поиска в поле **Библиотека событий** .</span><span class="sxs-lookup"><span data-stu-id="61225-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="61225-141">Например, если вы хотите найти событие **lock_acquired** , можно ввести **Lock**или **Lock**.</span><span class="sxs-lookup"><span data-stu-id="61225-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="61225-142">Выбранные события появляются в поле **Выбранные события** .</span><span class="sxs-lookup"><span data-stu-id="61225-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="61225-143">Чтобы удалить события из поля **Выбранные события** , щелкните стрелку влево.</span><span class="sxs-lookup"><span data-stu-id="61225-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="61225-144">После выбора событий для отслеживания нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61225-145">События из канала **Debug** скрыты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61225-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="61225-146">Чтобы просмотреть события отладки, выберите **Отладка** в раскрывающемся списке **Каналы** .</span><span class="sxs-lookup"><span data-stu-id="61225-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="61225-147">Захватить глобальные поля</span><span class="sxs-lookup"><span data-stu-id="61225-147">Capture Global Fields</span></span>  
 <span data-ttu-id="61225-148">Глобальные поля (также называемые действиями) можно использовать для связывания одного или нескольких действий с выбранными событиями.</span><span class="sxs-lookup"><span data-stu-id="61225-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="61225-149">Если выбран шаблон на странице **Выбор шаблона** , то все глобальные поля, определенные в шаблоне, отображаются на этой странице.</span><span class="sxs-lookup"><span data-stu-id="61225-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="61225-150">На странице **Выбор глобальных полей** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="61225-151">Выберите глобальные поля, которые необходимо отслеживать для сеанса событий, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="61225-152">Можно удалять или добавлять глобальные поля путем установки или снятия флажков рядом с соответствующими глобальными полями.</span><span class="sxs-lookup"><span data-stu-id="61225-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61225-153">Выбранные действия сортируются по **Имени** , что позволяет просматривать связанные действия в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="61225-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="61225-154">Доступна также сортировка по описанию и включенному или отключенному состоянию. Для этого нужно щелкнуть заголовок столбца рядом с именем поля.</span><span class="sxs-lookup"><span data-stu-id="61225-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="61225-155">Настройка фильтров событий сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="61225-156">Можно ограничивать отслеживаемые события с помощью фильтров (также называемых предикатами).</span><span class="sxs-lookup"><span data-stu-id="61225-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="61225-157">На странице **Настройка фильтров событий сеанса** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="61225-158">Если не используется стандартный шаблон, создайте собственные условия фильтра и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61225-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="61225-159">Если используется стандартный шаблон, то в разделе **Фильтры на основе шаблона (только для чтения)** в мастере новых сеансов отображается список фильтров, уже созданных на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="61225-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="61225-160">В разделе **Дополнительные фильтры** можно настроить дополнительные фильтры для сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="61225-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="61225-161">Настраиваемые фильтры применяются ко всем выбранным событиям.</span><span class="sxs-lookup"><span data-stu-id="61225-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="61225-162">Мастер новых шаблонов не поддерживает настройку фильтров для отдельного события.</span><span class="sxs-lookup"><span data-stu-id="61225-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61225-163">При настройке предложения группирования для фильтра лишние круглые скобки будут удалены из фильтра после сохранения результата.</span><span class="sxs-lookup"><span data-stu-id="61225-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="61225-164">Например, при создании фильтра группирования **Предложения 1** и **Предложения 2**предложения будут заключаться в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="61225-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="61225-165">После сохранения фильтра лишние круглые скобки будут удалены.</span><span class="sxs-lookup"><span data-stu-id="61225-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="61225-166">Удаление круглых скобок не влияет на логику фильтрации.</span><span class="sxs-lookup"><span data-stu-id="61225-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="61225-167">Укажите хранилище данных сеанса</span><span class="sxs-lookup"><span data-stu-id="61225-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="61225-168">Метод сбора данных для анализа указывается на странице **Настройка хранилища данных сеанса** .</span><span class="sxs-lookup"><span data-stu-id="61225-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="61225-169">Подсистема расширенных событий SQL Server использует целевые объекты для вывода данных.</span><span class="sxs-lookup"><span data-stu-id="61225-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="61225-170">Целевые объекты хранят в себе данные и могут выполнять такие действия, как запись в файл или статистическая обработка данных событий.</span><span class="sxs-lookup"><span data-stu-id="61225-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="61225-171">Выберите метод сбора данных для анализа и на странице **Настройка хранилища данных сеанса** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="61225-172">Для больших наборов данных и создания записей журнала установите флажок **Сохранять данные в файл для последующего анализа** , затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="61225-173">В поле **Имя файла на сервере** введите путь и имя файла либо нажмите кнопку **Обзор** , чтобы указать каталог файлов на сервере, где следует сохранять данные.</span><span class="sxs-lookup"><span data-stu-id="61225-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="61225-174">В поле **Максимальный размер файла** укажите максимальный размер файла, который будет использоваться в качестве целевого.</span><span class="sxs-lookup"><span data-stu-id="61225-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="61225-175">Если максимальный размер файла не задан, файл будет увеличиваться до заполнения диска.</span><span class="sxs-lookup"><span data-stu-id="61225-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="61225-176">Размер файла по умолчанию составляет 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="61225-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="61225-177">Установите флажок **Включить переключение файлов** , чтобы разрешить включить переключение файлов.</span><span class="sxs-lookup"><span data-stu-id="61225-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="61225-178">В поле **Максимальное число файлов** введите максимальное число файлов, которые следует сохранять в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="61225-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="61225-179">Для сбора недавних данных установите флажок **Работать только с самыми последними данными (цель "кольцевой буфер")** , затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="61225-180">В поле **Число сохраняемых событий** введите или выберите число сохраняемых событий с помощью стрелок вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="61225-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="61225-181">В поле **Максимальный размер буферной памяти** укажите максимальный объем буферной памяти.</span><span class="sxs-lookup"><span data-stu-id="61225-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="61225-182">Существующие события будут удалены по достижении этого значения.</span><span class="sxs-lookup"><span data-stu-id="61225-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="61225-183">Чтобы в буфере сохранялось указанное число событий каждого типа, установите флажок **Оставить заданное число событий (каждого типа) при переполнении буфера** .</span><span class="sxs-lookup"><span data-stu-id="61225-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="61225-184">В поле **Число сохраняемых событий (каждого типа)** введите или выберите число сохраняемых событий (каждого типа) с помощью стрелок вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="61225-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="61225-185">Сводка</span><span class="sxs-lookup"><span data-stu-id="61225-185">Summary</span></span>  
 <span data-ttu-id="61225-186">На странице **Сводка** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="61225-187">Проверьте правильность выбора.</span><span class="sxs-lookup"><span data-stu-id="61225-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="61225-188">Разверните узлы сеанса событий, чтобы убедиться, что все выбранные события будут включены в сеанс событий.</span><span class="sxs-lookup"><span data-stu-id="61225-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="61225-189">Нажмите кнопку **Скрипт** для экспорта скрипта создания сеанса в новое окно редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="61225-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="61225-190">Чтобы создать сеанс событий, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="61225-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="61225-191">Создание сеанса событий</span><span class="sxs-lookup"><span data-stu-id="61225-191">Create Event Session</span></span>  
 <span data-ttu-id="61225-192">На странице **Создание сеанса событий** после успешного создания сеанса событий выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61225-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="61225-193">Выберите параметр **Запуск сеанса событий непосредственно после создания сеанса** , чтобы сеанс запустился сразу после закрытия мастера.</span><span class="sxs-lookup"><span data-stu-id="61225-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="61225-194">Для просмотра данных, передаваемых в режиме реального времени, сеанс событий нужно запустить сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="61225-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="61225-195">Для просмотра данных, передаваемых в режиме реального времени для этого сеанса, щелкните **Отображать данные в режиме реального времени по мере их отслеживания** .</span><span class="sxs-lookup"><span data-stu-id="61225-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="61225-196">Данные, передаваемые в режиме реального времени, будут отображаться сразу после создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="61225-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61225-197">См. также:</span><span class="sxs-lookup"><span data-stu-id="61225-197">See Also</span></span>  
 [<span data-ttu-id="61225-198">Создание сеанса расширенных событий в диалоговом окне «Создание сеанса»</span><span class="sxs-lookup"><span data-stu-id="61225-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
