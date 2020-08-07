---
title: Справка F1 мастера управления секциями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729425"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="7b8ea-102">Справка F1 мастера управления секциями</span><span class="sxs-lookup"><span data-stu-id="7b8ea-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="7b8ea-103">**Мастер управления секциями** используется для управления и изменения существующих секционированных таблиц с помощью переключения секций или реализации сценария скользящего окна.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="7b8ea-104">Этот мастер облегчает управление секциями и упрощает регулярный перенос данных в таблицы и из них.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="7b8ea-105">Запуск мастера управления секциями</span><span class="sxs-lookup"><span data-stu-id="7b8ea-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="7b8ea-106">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите базу данных, щелкните правой кнопкой мыши таблицу, в которой необходимо создать секцию, укажите пункт **Хранилище**, а затем выберите **Управление секцией**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="7b8ea-107">`Note`Если **Управление секцией** недоступно, возможно, выбрана таблица, которая не содержит секций.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="7b8ea-108">Выберите команду **Создать секцию** из вложенного меню **Хранилище** и воспользуйтесь **Мастером создания секций** , чтобы создать секции в таблице.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="7b8ea-109">Дополнительные сведения о секциях и индексах см. в разделе [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="7b8ea-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="7b8ea-110">В этом разделе содержатся сведения, необходимые для управления, изменения и реализации секций с помощью **Мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="7b8ea-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7b8ea-111">In This Section</span></span>  
 <span data-ttu-id="7b8ea-112">Следующие разделы содержат справку по страницам **Мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="7b8ea-113">Мастер управления секциями (страница «Выбор действия над секцией»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="7b8ea-114">Мастер управления секциями (страница входящего переключения)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="7b8ea-115">Мастер управления секциями (страница исходящего переключения)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="7b8ea-116">Мастер управления секциями (страница «Выбор параметров промежуточной таблицы»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="7b8ea-117">Мастер управления секциями (страница «Выбор режима вывода»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="7b8ea-118">Мастер управления секциями (страница «Создание расписания задания»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="7b8ea-119">Мастер управления секциями (страница «Сводка»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="7b8ea-120">Мастер управления секциями (страница «Выполнение»)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="7b8ea-121">Страница «Выбор действия над секцией»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="7b8ea-122">Страница **Выбор действия над секцией** служит для выбора действия, которое следует выполнить над секцией.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="7b8ea-123">Создание промежуточной таблицы</span><span class="sxs-lookup"><span data-stu-id="7b8ea-123">Create a Staging Table</span></span>  
 <span data-ttu-id="7b8ea-124">Переключение секций — стандартная задача секционирования при наличии секционированной таблицы, в которую и из которой регулярно выполняется перенос данных; например, имеется секционированная таблица с текущими квартальными данными, и нужно перемещать в нее новые данные, выполнив архивацию старых, в конце каждого квартала.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="7b8ea-125">Мастер создает промежуточную таблицу с тем же столбцом секционирования, структурой таблиц и столбцов и индексами и сохраняет новую таблицу в файловой группе, в которой расположена исходная секция.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="7b8ea-126">Чтобы создать промежуточную таблицу для входящего или исходящего переключения данных секционирования, выберите команду **Создать промежуточную таблицу для переключения секции**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="7b8ea-127">Сценарий со скользящим окном</span><span class="sxs-lookup"><span data-stu-id="7b8ea-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="7b8ea-128">Для управления секциями в сценарии со скользящим окном выберите команду **Управлять секционированными данными в сценарии со скользящим окном**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7b8ea-129">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7b8ea-129">UI element list</span></span>  
 <span data-ttu-id="7b8ea-130">**Создать промежуточную таблицу для переключения секции**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="7b8ea-131">Создает промежуточную таблицу для данных, подвергаемых входящему или исходящему переключению в существующей секционированной таблице.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="7b8ea-132">**Выполнить исходящее переключение секции**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-132">**Switch out partition**</span></span>  
 <span data-ttu-id="7b8ea-133">Предоставляет параметры удаления секции из таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="7b8ea-134">**Выполнить входящее переключение секции**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-134">**Switch in partition**</span></span>  
 <span data-ttu-id="7b8ea-135">Предоставляет параметры добавления секции в таблицу.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="7b8ea-136">**Управлять секционированными данными в сценарии со скользящим окном**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="7b8ea-137">Присоединяет пустую секцию к существующей таблице для входящего переключения данных.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="7b8ea-138">На данный момент мастер поддерживает входящее переключение последней секции и исходящее — первой.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="7b8ea-139">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="7b8ea-140">Страница «Выбор параметров переключения секций»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="7b8ea-141">Чтобы выбрать промежуточную таблицу для входящего переключения в секционированную таблицу, воспользуйтесь страницей **Выбор параметров переключения секций** .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7b8ea-142">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7b8ea-142">UI element list</span></span>  
 <span data-ttu-id="7b8ea-143">**Показать все секции**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="7b8ea-144">Выберите для отображения всех секций, включая секции, в настоящее время находящиеся в секционированной таблице.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="7b8ea-145">**Сетка секций**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-145">**Partition grid**</span></span>  
 <span data-ttu-id="7b8ea-146">Отображает имя секции, а также параметры **Левая граница**, **Правая граница**, **Файловая группа**и **Число строк** для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="7b8ea-147">**Таблица входящего переключения**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-147">**Switch in table**</span></span>  
 <span data-ttu-id="7b8ea-148">Выберите промежуточную таблицу, содержащую секцию, которую нужно добавить в секционированную таблицу.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="7b8ea-149">Это таблицу следует создать до переключения секций с помощью **мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="7b8ea-150">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="7b8ea-151">Страница «Выбор параметров исходящего переключения секций»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="7b8ea-152">Чтобы выбрать секцию и промежуточную таблицу для хранения секционированных данных, подвергающихся исходящему переключению в секционированной таблице, воспользуйтесь страницей **Выбор параметров исходящего переключения секций** .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7b8ea-153">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7b8ea-153">UI element list</span></span>  
 <span data-ttu-id="7b8ea-154">**Сетка секций**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-154">**Partition grid**</span></span>  
 <span data-ttu-id="7b8ea-155">Отображает имя секции, а также параметры **Левая граница**, **Правая граница**, **Файловая группа**и **Число строк** для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="7b8ea-156">**Таблица исходящего переключения**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-156">**Switch out table**</span></span>  
 <span data-ttu-id="7b8ea-157">Выберите новую таблицу или существующую таблицу для исходящего переключения на нее данных.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="7b8ea-158">**Создать**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-158">**New**</span></span>  
 <span data-ttu-id="7b8ea-159">Введите новое имя для промежуточной таблицы, которую необходимо использовать для исходящего переключения секций текущей исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="7b8ea-160">**Существующая**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-160">**Existing**</span></span>  
 <span data-ttu-id="7b8ea-161">Выберите существующую промежуточную таблицу, которую необходимо использовать для исходящего переключения секций текущей исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="7b8ea-162">Если существующая таблица содержит данные, они будут перезаписаны данными, подвергаемыми исходящему переключению.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="7b8ea-163">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="7b8ea-164">Страница «Выбор параметров промежуточной таблицы»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="7b8ea-165">Чтобы создать промежуточную таблицу для переключения секционированных данных, воспользуйтесь страницей **Выбор параметров промежуточной таблицы** .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="7b8ea-166">Промежуточные таблицы должны располагаться в той же файловой группе выбранной секции, в которой расположена исходная таблица.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="7b8ea-167">Промежуточная таблица должна зеркально отображать структуру как исходной таблицы, так и целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="7b8ea-168">В промежуточной таблице можно также создать те же индексы, что и в исходной секции.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="7b8ea-169">Промежуточная таблица автоматически включает в себя ограничение в зависимости от элементов исходной секции.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="7b8ea-170">Это ограничение обычно создается на основе граничного значения исходной секции.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7b8ea-171">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7b8ea-171">UI element list</span></span>  
 <span data-ttu-id="7b8ea-172">**Имя промежуточной таблицы**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-172">**Staging table name**</span></span>  
 <span data-ttu-id="7b8ea-173">Создайте имя для промежуточной таблицы или оставьте имя по умолчанию, отображаемое в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="7b8ea-174">**Переключить секцию**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-174">**Switch partition**</span></span>  
 <span data-ttu-id="7b8ea-175">Выберите исходную секцию, которая подлежит исходящему переключению из текущей таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="7b8ea-176">**Новое граничное значение**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-176">**New boundary value**</span></span>  
 <span data-ttu-id="7b8ea-177">Выберите или введите нужное граничное значение для секции промежуточной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="7b8ea-178">**Файловая группа**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-178">**Filegroup**</span></span>  
 <span data-ttu-id="7b8ea-179">Выберите файловую группу для новой таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="7b8ea-180">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="7b8ea-181">Страница «Выбор параметров вывода»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-181">Select Output Option Page</span></span>  
 <span data-ttu-id="7b8ea-182">Воспользуйтесь страницей **Выбор параметров вывода** для указания способа внесения изменений в секции.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="7b8ea-183">Создать скрипт</span><span class="sxs-lookup"><span data-stu-id="7b8ea-183">Create Script</span></span>  
 <span data-ttu-id="7b8ea-184">Когда мастер закончит работу, он создаст скрипт в редакторе запросов для изменения секций таблицы.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="7b8ea-185">Если нужно просмотреть скрипт и выполнить его вручную, выберите **Создать скрипт** .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="7b8ea-186">**Вывести скрипт в файл**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-186">**Script to file**</span></span>  
 <span data-ttu-id="7b8ea-187">Вывести скрипт в SQL-файл.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="7b8ea-188">Укажите **Unicode** или **текст ANSI**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="7b8ea-189">Чтобы указать имя и расположение файла, нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="7b8ea-190">**Вывести скрипт в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="7b8ea-191">Сохранить скрипт в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="7b8ea-192">**Вывести скрипт в новое окно запроса**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="7b8ea-193">Сформировать скрипт в окне редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="7b8ea-194">Если не открыто ни одного окна редактора, то в качестве места назначения для скрипта откроется новое окно редактора.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="7b8ea-195">Запустить немедленно</span><span class="sxs-lookup"><span data-stu-id="7b8ea-195">Run Immediately</span></span>  
 <span data-ttu-id="7b8ea-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-196">**Run immediately**</span></span>  
 <span data-ttu-id="7b8ea-197">По нажатию кнопки **Далее** или **Готово**мастер внесет изменения в секции.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="7b8ea-198">Расписание</span><span class="sxs-lookup"><span data-stu-id="7b8ea-198">Schedule</span></span>  
 <span data-ttu-id="7b8ea-199">Выберите этот параметр, чтобы изменить секции таблицы в назначенную дату и время.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="7b8ea-200">**Изменить расписание**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-200">**Change schedule**</span></span>  
 <span data-ttu-id="7b8ea-201">Открывает диалоговое окно **Создание расписания задания** , в котором вы можете выбрать, просмотреть и изменить свойства запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="7b8ea-202">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="7b8ea-203">Страница «Создание расписания задания»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="7b8ea-204">Страница **Создание расписания задания** предназначена для просмотра и изменения свойств расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b8ea-205">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b8ea-205">Options</span></span>  
 <span data-ttu-id="7b8ea-206">Выберите тип расписания для задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="7b8ea-207">**имя**;</span><span class="sxs-lookup"><span data-stu-id="7b8ea-207">**Name**</span></span>  
 <span data-ttu-id="7b8ea-208">Введите новое имя для расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="7b8ea-209">**Задания в расписании**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="7b8ea-210">Просмотр существующих заданий, использующих расписание.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="7b8ea-211">**Тип расписания**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-211">**Schedule type**</span></span>  
 <span data-ttu-id="7b8ea-212">Выбор типа расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="7b8ea-213">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-213">**Enabled**</span></span>  
 <span data-ttu-id="7b8ea-214">Включение или отключение расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="7b8ea-215">Параметры повторяющихся расписаний</span><span class="sxs-lookup"><span data-stu-id="7b8ea-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="7b8ea-216">Выберите частоту выполнения запланированной задачи.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="7b8ea-217">**Выполняется**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-217">**Occurs**</span></span>  
 <span data-ttu-id="7b8ea-218">Выберите интервал повторения расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="7b8ea-219">**Повторять каждые**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-219">**Recurs every**</span></span>  
 <span data-ttu-id="7b8ea-220">Укажите число дней или недель между повторениями расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="7b8ea-221">Этот параметр недоступен для ежемесячных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-222">**Понедельник**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-222">**Monday**</span></span>  
 <span data-ttu-id="7b8ea-223">Назначает выполнение задания на понедельник.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="7b8ea-224">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-225">**Вторник**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-225">**Tuesday**</span></span>  
 <span data-ttu-id="7b8ea-226">Назначает выполнение задания на вторник.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="7b8ea-227">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-228">**Среда**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-228">**Wednesday**</span></span>  
 <span data-ttu-id="7b8ea-229">Назначает выполнение задания на среду.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="7b8ea-230">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-231">**Четверг**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-231">**Thursday**</span></span>  
 <span data-ttu-id="7b8ea-232">Назначает выполнение задачи на четверг.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="7b8ea-233">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-234">**Пятница**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-234">**Friday**</span></span>  
 <span data-ttu-id="7b8ea-235">Назначает выполнение задачи на пятницу.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="7b8ea-236">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-237">**Суббота**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-237">**Saturday**</span></span>  
 <span data-ttu-id="7b8ea-238">Назначает выполнение задачи на субботу.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="7b8ea-239">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-240">**Воскресенье**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-240">**Sunday**</span></span>  
 <span data-ttu-id="7b8ea-241">Назначает выполнение задачи на воскресенье.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="7b8ea-242">Этот параметр доступен только для еженедельных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-243">**День**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-243">**Day**</span></span>  
 <span data-ttu-id="7b8ea-244">Указывает, в какой день месяца должно появляться расписание.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="7b8ea-245">Этот параметр доступен только для ежемесячных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-246">**каждого**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-246">**of every**</span></span>  
 <span data-ttu-id="7b8ea-247">Выберите количество месяцев между повторениями расписания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="7b8ea-248">Этот параметр доступен только для ежемесячных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-249">**Это**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-249">**The**</span></span>  
 <span data-ttu-id="7b8ea-250">Задайте расписание для определенного дня недели в выбранную неделю месяца.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="7b8ea-251">Этот параметр доступен только для ежемесячных расписаний.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="7b8ea-252">**Выполняется раз в**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-252">**Occurs once at**</span></span>  
 <span data-ttu-id="7b8ea-253">Укажите время, когда должно выполняться ежедневное задание.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="7b8ea-254">**Выполняется каждые**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-254">**Occurs every**</span></span>  
 <span data-ttu-id="7b8ea-255">Установите количество часов или минут между выполнениями.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="7b8ea-256">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-256">**Start date**</span></span>  
 <span data-ttu-id="7b8ea-257">Задайте дату, когда расписание вступит в силу.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="7b8ea-258">**Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-258">**End date**</span></span>  
 <span data-ttu-id="7b8ea-259">Задайте дату, когда расписание перестанет действовать.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="7b8ea-260">**Без даты окончания**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-260">**No end date**</span></span>  
 <span data-ttu-id="7b8ea-261">Укажите, что расписание будет действовать без временных ограничений.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="7b8ea-262">Параметры однократных типов расписаний</span><span class="sxs-lookup"><span data-stu-id="7b8ea-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="7b8ea-263">Если запланировано однократное выполнение задачи, выберите дату и время (не ранее текущих).</span><span class="sxs-lookup"><span data-stu-id="7b8ea-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="7b8ea-264">**Дата**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-264">**Date**</span></span>  
 <span data-ttu-id="7b8ea-265">Выберите дату выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="7b8ea-266">**Time**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-266">**Time**</span></span>  
 <span data-ttu-id="7b8ea-267">Выберите время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="7b8ea-268">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="7b8ea-269">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-269">Summary Page</span></span>  
 <span data-ttu-id="7b8ea-270">Воспользуйтесь страницей **Сводка** для просмотра параметров, выбранных на предыдущих страницах.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7b8ea-271">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7b8ea-271">UI element list</span></span>  
 <span data-ttu-id="7b8ea-272">**Просмотрите выбранные параметры**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-272">**Review your selections**</span></span>  
 <span data-ttu-id="7b8ea-273">Показывает выбранные варианты на всех страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="7b8ea-274">Щелкните узел, чтобы развернуть и просмотреть выбранные ранее параметры.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="7b8ea-275">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="7b8ea-276">Страница «Ход выполнения»</span><span class="sxs-lookup"><span data-stu-id="7b8ea-276">Progress Page</span></span>  
 <span data-ttu-id="7b8ea-277">Страница **Ход выполнения** служит для наблюдения за сведениями о состоянии действий **мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="7b8ea-278">В зависимости от действий, выбранных в мастере, страница **Выполнение** может содержать одно или несколько действий.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="7b8ea-279">В верхнем поле показано общее состояние мастера и число полученных им сообщений о состоянии, предупреждений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b8ea-280">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b8ea-280">Options</span></span>  
 <span data-ttu-id="7b8ea-281">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-281">**Details**</span></span>  
 <span data-ttu-id="7b8ea-282">Сведения о событии, состоянии и любых сообщениях, которые возвращены в результате действий мастера.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="7b8ea-283">**Действие**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-283">**Action**</span></span>  
 <span data-ttu-id="7b8ea-284">Задает тип и имя каждого действия.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="7b8ea-285">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-285">**Status**</span></span>  
 <span data-ttu-id="7b8ea-286">Указывает, вернуло ли действие мастера в целом значение **Успешно** или **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="7b8ea-287">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-287">**Message**</span></span>  
 <span data-ttu-id="7b8ea-288">Любые сообщения об ошибках или предупреждения от процесса.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="7b8ea-289">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-289">**Stop**</span></span>  
 <span data-ttu-id="7b8ea-290">Остановить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="7b8ea-291">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-291">**Report**</span></span>  
 <span data-ttu-id="7b8ea-292">Создание отчета, содержащего результаты **мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="7b8ea-293">Доступны следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7b8ea-293">The options are:</span></span>  
  
-   <span data-ttu-id="7b8ea-294">**Просмотреть отчет**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-294">**View Report**</span></span>  
  
-   <span data-ttu-id="7b8ea-295">**Сохранить отчет в файл**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="7b8ea-296">**Копировать отчет в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="7b8ea-297">**Отправить отчет по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="7b8ea-298">**Просмотреть отчет**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-298">**View Report**</span></span>  
 <span data-ttu-id="7b8ea-299">Откройте диалоговое окно **Просмотр отчета** .</span><span class="sxs-lookup"><span data-stu-id="7b8ea-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="7b8ea-300">Это диалоговое окно содержит текстовый отчет о ходе работы **мастера управления секциями**.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="7b8ea-301">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="7b8ea-301">**Close**</span></span>  
 <span data-ttu-id="7b8ea-302">Завершение работы мастера.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="7b8ea-303">![Значок стрелки, используемый со ссылкой "В начало"](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [В этом разделе](#Top)</span><span class="sxs-lookup"><span data-stu-id="7b8ea-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8ea-304">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b8ea-304">See Also</span></span>  
 [<span data-ttu-id="7b8ea-305">Partitioned Tables and Indexes</span><span class="sxs-lookup"><span data-stu-id="7b8ea-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
