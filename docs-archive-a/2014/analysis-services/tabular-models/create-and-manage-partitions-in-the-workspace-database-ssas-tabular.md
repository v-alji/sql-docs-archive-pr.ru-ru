---
title: Создание секций и управление ими в базе данных рабочей области (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657922"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="312ed-102">Создание и управление секциями в базе данных рабочей области (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="312ed-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="312ed-103">Секции разделяют таблицу на логические части.</span><span class="sxs-lookup"><span data-stu-id="312ed-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="312ed-104">Все секции можно обработать (обновить) независимо или параллельно с другими секциями.</span><span class="sxs-lookup"><span data-stu-id="312ed-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="312ed-105">Использование секций позволяет улучшить масштабируемость и управление базами данных большого размера.</span><span class="sxs-lookup"><span data-stu-id="312ed-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="312ed-106">По умолчанию все таблицы содержат одну секцию, включающую все столбцы.</span><span class="sxs-lookup"><span data-stu-id="312ed-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="312ed-107">Задачи в этом разделе описывают создание секций и управление ими в базе данных рабочей области модели с помощью диалогового окна « **Диспетчер секций** » в среде[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="312ed-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="312ed-108">После завершения развертывания модели в другом экземпляре служб Analysis Services администраторы базы данных могут создавать секции и управлять ими в (развернутой) модели с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="312ed-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="312ed-109">Дополнительные сведения см. в разделе [Создание секций табличной модели и управление ими (табличные службы SSAS)](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="312ed-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="312ed-110">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="312ed-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="312ed-111">Создание новой секции</span><span class="sxs-lookup"><span data-stu-id="312ed-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="312ed-112">Копирование секции</span><span class="sxs-lookup"><span data-stu-id="312ed-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="312ed-113">Удаление секции</span><span class="sxs-lookup"><span data-stu-id="312ed-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="312ed-114">В базе данных рабочей области модели нельзя выполнять слияние секций с помощью диалогового окна «Диспетчер секций».</span><span class="sxs-lookup"><span data-stu-id="312ed-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="312ed-115">Слияние секций в развернутой модели можно выполнить только с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="312ed-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="312ed-116">Задания</span><span class="sxs-lookup"><span data-stu-id="312ed-116">Tasks</span></span>  
 <span data-ttu-id="312ed-117">Для создания секций и управления ими используется диалоговое окно **Диспетчер секций** .</span><span class="sxs-lookup"><span data-stu-id="312ed-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="312ed-118">Для вывода диалогового окна **Диспетчер секций** в приложении [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]в меню **Таблица** выберите **Секции**.</span><span class="sxs-lookup"><span data-stu-id="312ed-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="312ed-119">Создание новой секции</span><span class="sxs-lookup"><span data-stu-id="312ed-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="312ed-120">В конструкторе моделей выберите таблицу, для которой необходимо определить секцию.</span><span class="sxs-lookup"><span data-stu-id="312ed-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="312ed-121">В меню **Таблица** выберите **Секции**.</span><span class="sxs-lookup"><span data-stu-id="312ed-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="312ed-122">В **Диспетчере секций**в поле списка **Таблица** выберите таблицу для секционирования и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="312ed-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="312ed-123">В поле **Имя секции**введите имя секции.</span><span class="sxs-lookup"><span data-stu-id="312ed-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="312ed-124">По умолчанию к имени секции, заданной по умолчанию, будет добавляться номер, постепенно увеличивающийся для каждой новой секции.</span><span class="sxs-lookup"><span data-stu-id="312ed-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="312ed-125">Строки и столбцы для включения в секцию можно выбрать с помощью режима предварительного просмотра таблиц или с помощью SQL-запроса, созданного в режиме редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="312ed-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="312ed-126">Чтобы выбрать режим предварительного просмотра в виде таблицы (по умолчанию), нажмите кнопку **Просмотр таблицы** , расположенную в верхнем правом углу окна предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="312ed-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="312ed-127">Выберите столбцы, которые необходимо включить в секцию, установив флажок рядом с именем столбца.</span><span class="sxs-lookup"><span data-stu-id="312ed-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="312ed-128">Для фильтрации строк щелкните правой кнопкой мыши значение ячейки и выберите **Фильтрация по выбранному значению ячейки**.</span><span class="sxs-lookup"><span data-stu-id="312ed-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="312ed-129">Чтобы выбрать инструкцию SQL, нажмите кнопку **Редактор запросов** в правом верхнем углу окна предварительного просмотра, а затем введите вручную или вставьте инструкцию SQL-запроса в окно запроса.</span><span class="sxs-lookup"><span data-stu-id="312ed-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="312ed-130">Чтобы проверить инструкцию, нажмите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="312ed-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="312ed-131">Нажмите кнопку **Конструктор**, чтобы открыть конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="312ed-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="312ed-132">Копирование секции</span><span class="sxs-lookup"><span data-stu-id="312ed-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="312ed-133">В **Диспетчере секций**в поле списка **Таблица** выберите таблицу, содержащую секцию, которую необходимо копировать.</span><span class="sxs-lookup"><span data-stu-id="312ed-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="312ed-134">В списке **Секции** выберите секцию, которую необходимо копировать, и нажмите кнопку **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="312ed-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="312ed-135">В поле **Имя секции**введите новое имя секции.</span><span class="sxs-lookup"><span data-stu-id="312ed-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="312ed-136">Удаление секции</span><span class="sxs-lookup"><span data-stu-id="312ed-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="312ed-137">В **Диспетчере секций**в поле списка **Таблица** выберите таблицу, содержащую секцию, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="312ed-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="312ed-138">В списке **Секции** выберите секцию, которую необходимо удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="312ed-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312ed-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="312ed-139">See Also</span></span>  
 <span data-ttu-id="312ed-140">[Секции &#40;табличные&#41;SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="312ed-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="312ed-141">Обработка секций в базе данных рабочей области &#40;табличных&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="312ed-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
