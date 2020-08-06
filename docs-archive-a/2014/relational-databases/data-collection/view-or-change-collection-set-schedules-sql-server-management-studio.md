---
title: Просмотр и изменение расписаний для набора элементов сбора (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667228"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="ba46a-102">Просмотр и изменение расписаний набора элементов сбора (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ba46a-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ba46a-103">Просмотр и изменение расписаний набора элементов сбора производится в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba46a-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ba46a-104">Режим сбора, с кэшированием или без кэширования, определяет способ внесения изменений в расписание.</span><span class="sxs-lookup"><span data-stu-id="ba46a-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="ba46a-105">В режиме с кэшированием используются отдельные расписания для сбора и передачи.</span><span class="sxs-lookup"><span data-stu-id="ba46a-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="ba46a-106">В режиме без кэширования для сбора и передачи используется одно расписание.</span><span class="sxs-lookup"><span data-stu-id="ba46a-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="ba46a-107">Для каждого из системных наборов сбора данных используется следующий тип режима сбора:</span><span class="sxs-lookup"><span data-stu-id="ba46a-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="ba46a-108">**Занято места на диске** использует режим сбора без кэширования.</span><span class="sxs-lookup"><span data-stu-id="ba46a-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="ba46a-109">**Статистика запросов** использует режим сбора с кэшированием.</span><span class="sxs-lookup"><span data-stu-id="ba46a-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="ba46a-110">**Активность сервера** использует режим сбора с кэшированием.</span><span class="sxs-lookup"><span data-stu-id="ba46a-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="ba46a-111">Просмотр расписаний набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="ba46a-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="ba46a-112">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**и узел **Наборы элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="ba46a-113">Щелкните правой кнопкой имя набора сбора и выберите пункт **Свойства** , чтобы открыть диалоговое окно [Свойства набора сбора данных](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="ba46a-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="ba46a-114">Изменение расписаний набора элементов сбора в режиме с кэшированием</span><span class="sxs-lookup"><span data-stu-id="ba46a-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="ba46a-115">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**и узел **Наборы элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="ba46a-116">Щелкните правой кнопкой набор элементов сбора, который использует кэшированный режим, например **Статистика запросов**, а затем выберите **Свойства** , чтобы открыть диалоговое окно [Свойства набора сбора данных](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="ba46a-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="ba46a-117">Частоту сбора можно изменить на странице **Общие** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="ba46a-118">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ba46a-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="ba46a-119">На панели сведений дважды щелкните число в столбце **Частота сбора (в секундах)** в таблице **Элементы сбора** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="ba46a-120">Чтобы увеличить или уменьшить частоту сбора, введите нужное число и нажмите клавишу ВВОД, чтобы сохранить новое значение.</span><span class="sxs-lookup"><span data-stu-id="ba46a-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="ba46a-121">Чтобы изменить существующее расписание передачи набора элементов сбора, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ba46a-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="ba46a-122">Перейдите на страницу **Передачи** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="ba46a-123">В панели сведений нажмите **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="ba46a-124">Откроется диалоговое окно **Выбор расписания для задания** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="ba46a-125">Доступные расписания отображаются в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="ba46a-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="ba46a-126">Щелкните строку с нужным расписанием.</span><span class="sxs-lookup"><span data-stu-id="ba46a-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="ba46a-127">Например, чтобы установить сбор раз в 5 минут, щелкните строку, где имя расписания равно **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ba46a-128">Чтобы просмотреть и изменить свойства выбранного расписания, щелкните пункт **Свойства** , чтобы открыть диалоговое окно **Свойства расписания задания** для данного расписания.</span><span class="sxs-lookup"><span data-stu-id="ba46a-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="ba46a-129">Используйте данное диалоговое окно для изменения сведений о расписании, например частоты.</span><span class="sxs-lookup"><span data-stu-id="ba46a-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="ba46a-130">Вместо изменения существующего расписания можно создать новое расписание передачи, нажав кнопку **Создать** на странице **Передачи** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="ba46a-131">Это действие открывает диалоговое окно **Создание расписания задания** , которое служит для создания пользовательского расписания.</span><span class="sxs-lookup"><span data-stu-id="ba46a-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="ba46a-132">После изменения расписания нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="ba46a-133">Внесенные изменения отражаются на странице **Загрузки** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="ba46a-134">Нажмите кнопку **ОК** , чтобы сохранить изменения в частоте сбора и расписании передачи, а затем закройте диалоговое окно **Набор элементов сбора системных данных** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="ba46a-135">Изменение расписания набора элементов сбора в режиме без кэширования</span><span class="sxs-lookup"><span data-stu-id="ba46a-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="ba46a-136">В обозревателе объектов разверните узел **Управление** , затем узел **Сбор данных**и узел **Наборы элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="ba46a-137">Щелкните правой кнопкой набор элементов сбора, в котором используется режим без кэширования, например **Использование диска**, а затем выберите пункт **Свойства** , чтобы открыть диалоговое окно [Свойства набора сбора данных](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="ba46a-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="ba46a-138">Откроется диалоговое окно **Свойства набора элементов сбора данных** , где на вкладках будут представлены свойства набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="ba46a-139">Чтобы изменить расписание для этого набора элементов сбора, нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="ba46a-140">Откроется диалоговое окно **Выбор расписания для задания** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="ba46a-141">Доступные расписания отображаются в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="ba46a-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="ba46a-142">Щелкните строку с нужным расписанием.</span><span class="sxs-lookup"><span data-stu-id="ba46a-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="ba46a-143">Например, чтобы установить сбор раз в 5 минут, щелкните строку, где имя расписания равно **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba46a-144">Чтобы просмотреть и изменить свойства выбранного расписания, щелкните пункт **Свойства** , чтобы открыть диалоговое окно **Свойства расписания задания** для данного расписания.</span><span class="sxs-lookup"><span data-stu-id="ba46a-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="ba46a-145">Используйте данное диалоговое окно для изменения сведений о расписании, например частоты.</span><span class="sxs-lookup"><span data-stu-id="ba46a-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="ba46a-146">Вместо изменения существующего расписания можно создать новое расписание сбора и передачи, нажав кнопку **Создать** на странице **Общие** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="ba46a-147">В результате откроется диалоговое окно **Создание расписания задания** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="ba46a-148">После изменения расписания нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="ba46a-149">Чтобы сохранить изменения и закрыть диалоговое окно **Свойства набора элементов сбора данных** , нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ba46a-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="ba46a-150">Диалоговое окно «Свойства набора элементов сбора данных»</span><span class="sxs-lookup"><span data-stu-id="ba46a-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="ba46a-151">**Страница «Общие»**</span><span class="sxs-lookup"><span data-stu-id="ba46a-151">**General Page**</span></span>  
  
 <span data-ttu-id="ba46a-152">Эта страница используется для настройки методов сбора и передачи данных, расписаний и сроков хранения в хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ba46a-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="ba46a-153">На этой странице также содержатся сведения о наборах сбора, таких как типы сборщиков и частота сбора, и входных параметрах, используемых для набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="ba46a-154">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ba46a-154">**Name**</span></span>  
 <span data-ttu-id="ba46a-155">Отображает имя набора сбора, на который ссылается эта страница.</span><span class="sxs-lookup"><span data-stu-id="ba46a-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="ba46a-156">**Сбор и передача данных**</span><span class="sxs-lookup"><span data-stu-id="ba46a-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="ba46a-157">Указывает способы сбора данных и передачи в хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ba46a-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="ba46a-158">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="ba46a-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba46a-159">**Без кэширования. Сбор и передача данных по одному расписанию.**</span><span class="sxs-lookup"><span data-stu-id="ba46a-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="ba46a-160">Когда выбран этот параметр, укажите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ba46a-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="ba46a-161">**По запросу**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-161">**On-demand**.</span></span> <span data-ttu-id="ba46a-162">Сбор и передача данных по запросу.</span><span class="sxs-lookup"><span data-stu-id="ba46a-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="ba46a-163">**Расписание**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-163">**Schedule**.</span></span> <span data-ttu-id="ba46a-164">Сбор и передача данных по расписанию.</span><span class="sxs-lookup"><span data-stu-id="ba46a-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="ba46a-165">Щелкните **Выбрать** , чтобы выбрать из стандартного списка расписаний, или нажмите кнопку **Создать** , чтобы создать новое расписание.</span><span class="sxs-lookup"><span data-stu-id="ba46a-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="ba46a-166">**С применением кэширования. Сбор и кэширование данных осуществляются с заданной частотой сбора. Передача кэшируемых данных по отдельному расписанию.**</span><span class="sxs-lookup"><span data-stu-id="ba46a-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="ba46a-167">Сбор и кэширование данных с заданной частотой сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="ba46a-168">Передача собранных данных по отдельному расписанию.</span><span class="sxs-lookup"><span data-stu-id="ba46a-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="ba46a-169">**Элементы сбора**</span><span class="sxs-lookup"><span data-stu-id="ba46a-169">**Collection items**</span></span>  
 <span data-ttu-id="ba46a-170">Отображает элементы сбора в наборе сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="ba46a-171">Для каждого элемента сбора приводятся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ba46a-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="ba46a-172">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ba46a-172">**Name**</span></span>  
  
-   <span data-ttu-id="ba46a-173">**Тип сборщика**</span><span class="sxs-lookup"><span data-stu-id="ba46a-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="ba46a-174">**Частота сбора** (в секундах).</span><span class="sxs-lookup"><span data-stu-id="ba46a-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="ba46a-175">Это поле доступно для редактирования, если **Сбор и передача данных** настроены на применение кэширования.</span><span class="sxs-lookup"><span data-stu-id="ba46a-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="ba46a-176">Дважды щелкните эту ячейку, чтобы назначить частоту сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="ba46a-177">**Входные параметры**</span><span class="sxs-lookup"><span data-stu-id="ba46a-177">**Input parameters**</span></span>  
 <span data-ttu-id="ba46a-178">Отображает входные параметры для набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="ba46a-179">**Выполнять как**</span><span class="sxs-lookup"><span data-stu-id="ba46a-179">**Run as**</span></span>  
 <span data-ttu-id="ba46a-180">Указывает учетную запись для выполнения набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="ba46a-181">По умолчанию ею является учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba46a-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="ba46a-182">Если определены учетные записи-посредники, то в этот список входят имена доступных учетных записей-посредников.</span><span class="sxs-lookup"><span data-stu-id="ba46a-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="ba46a-183">**Указывает длительность хранения данных в хранилище данных управления**</span><span class="sxs-lookup"><span data-stu-id="ba46a-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="ba46a-184">Указывает длительность хранения собранных данных.</span><span class="sxs-lookup"><span data-stu-id="ba46a-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="ba46a-185">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="ba46a-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba46a-186">**Оставлять данные на**</span><span class="sxs-lookup"><span data-stu-id="ba46a-186">**Retain data for**</span></span>|<span data-ttu-id="ba46a-187">Этот параметр выбирается по умолчанию, а срок хранения по умолчанию — 14 дней.</span><span class="sxs-lookup"><span data-stu-id="ba46a-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="ba46a-188">**Оставлять данные на неопределенно долгое время**</span><span class="sxs-lookup"><span data-stu-id="ba46a-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="ba46a-189">Срок хранения данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="ba46a-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="ba46a-190">**Страница загрузки**</span><span class="sxs-lookup"><span data-stu-id="ba46a-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="ba46a-191">Эта страница используется для настройки расписания передачи данных, собранных этим набором сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba46a-192">Эта вкладка активна, только если для **Сбора и передачи данных** задан режим **Кэшированный**.</span><span class="sxs-lookup"><span data-stu-id="ba46a-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="ba46a-193">**Server**</span><span class="sxs-lookup"><span data-stu-id="ba46a-193">**Server**</span></span>  
 <span data-ttu-id="ba46a-194">Отображает имя сервера, на котором размещено хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ba46a-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="ba46a-195">Дополнительные сведения см. в статье [Настройка хранилища данных управления (среда SQL Server Management Studio)](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ba46a-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="ba46a-196">**Хранилище управляющих данных**</span><span class="sxs-lookup"><span data-stu-id="ba46a-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="ba46a-197">Отображает имя хранилища управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ba46a-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="ba46a-198">Дополнительные сведения см. в статье [Настройка хранилища данных управления (среда SQL Server Management Studio)](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ba46a-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="ba46a-199">**Последняя передача**</span><span class="sxs-lookup"><span data-stu-id="ba46a-199">**Last upload**</span></span>  
 <span data-ttu-id="ba46a-200">Отображает сведения о времени и дате для последней передачи, совершенной для набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="ba46a-201">**Расписание передачи**</span><span class="sxs-lookup"><span data-stu-id="ba46a-201">**Upload schedule**</span></span>  
 <span data-ttu-id="ba46a-202">Указывает расписание передачи для набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ba46a-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="ba46a-203">Если включено, щелкните **Выбрать** , чтобы выбрать из стандартного списка расписаний, или нажмите кнопку **Создать** , чтобы создать новое расписание.</span><span class="sxs-lookup"><span data-stu-id="ba46a-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="ba46a-204">**Страница описания**</span><span class="sxs-lookup"><span data-stu-id="ba46a-204">**Description Page**</span></span>  
  
 <span data-ttu-id="ba46a-205">Эта страница используется для просмотра описания набора сбора, на который указывает эта страница свойств.</span><span class="sxs-lookup"><span data-stu-id="ba46a-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba46a-206">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba46a-206">See Also</span></span>  
 <span data-ttu-id="ba46a-207">[Управление сбором данных](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="ba46a-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="ba46a-208">Сбор данных</span><span class="sxs-lookup"><span data-stu-id="ba46a-208">Data Collection</span></span>](data-collection.md)  
  
  
