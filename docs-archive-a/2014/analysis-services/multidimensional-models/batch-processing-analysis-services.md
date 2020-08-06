---
title: Пакетная обработка (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655415"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="046aa-102">Пакетная обработка (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="046aa-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="046aa-103">В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]вы можете использовать команду «Пакет», чтобы отправить несколько команд обработки на сервер в одном запросе.</span><span class="sxs-lookup"><span data-stu-id="046aa-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="046aa-104">Пакетная обработка позволяет выбирать объекты для обработки и управлять порядком их обработки.</span><span class="sxs-lookup"><span data-stu-id="046aa-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="046aa-105">Кроме того, пакет можно выполнить как серию изолированных заданий или как транзакцию, в которой сбой одного из процессов влечет за собой откат всего пакета.</span><span class="sxs-lookup"><span data-stu-id="046aa-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="046aa-106">Обработка пакетами увеличивает доступность данных за счет совмещения и уменьшения времени на фиксацию изменений.</span><span class="sxs-lookup"><span data-stu-id="046aa-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="046aa-107">При полной обработке измерения любая использующая его секция помечается как необработанная.</span><span class="sxs-lookup"><span data-stu-id="046aa-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="046aa-108">В результате этого кубы, содержащие необработанные секции, становятся недоступными для просмотра.</span><span class="sxs-lookup"><span data-stu-id="046aa-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="046aa-109">Эту ситуацию можно исправить, включив в задание пакетной обработки измерение вместе с соответствующими секциями.</span><span class="sxs-lookup"><span data-stu-id="046aa-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="046aa-110">При выполнении задания пакетной обработки как транзакции все включенные в транзакцию объекты останутся доступными для запросов до полного завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="046aa-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="046aa-111">После того как транзакция зафиксирована, на затронутые объекты налагается блокировка, что временно делает их недоступными, однако при этом суммарное количество времени на фиксацию оказывается меньше по сравнению с обработкой объектов по одному.</span><span class="sxs-lookup"><span data-stu-id="046aa-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="046aa-112">Процедура, приведенная в данном разделе, описывает шаги, необходимые для полной обработки измерений и секций.</span><span class="sxs-lookup"><span data-stu-id="046aa-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="046aa-113">При пакетной обработке могут использоваться и другие параметры, например параметры добавочной обработки.</span><span class="sxs-lookup"><span data-stu-id="046aa-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="046aa-114">Для правильного функционирования данных процедур необходимо использовать существующую базу данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащую по меньшей мере два измерения и одну секцию.</span><span class="sxs-lookup"><span data-stu-id="046aa-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="046aa-115">Этот раздел включает следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="046aa-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="046aa-116">Пакетная обработка в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="046aa-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="046aa-117">Пакетная обработка с использованием XMLA в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="046aa-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a> <span data-ttu-id="046aa-118">Пакетная обработка в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="046aa-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="046aa-119">Прежде чем обрабатывать объекты в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], необходимо произвести развертывание содержащего их проекта.</span><span class="sxs-lookup"><span data-stu-id="046aa-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="046aa-120">Дополнительные сведения см. в статье [Развертывание проектов служб Analysis Services (среда SSDT)](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="046aa-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="046aa-121">Откройте среду [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="046aa-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="046aa-122">Откройте развернутый проект.</span><span class="sxs-lookup"><span data-stu-id="046aa-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="046aa-123">В обозревателе решений откройте папку **Измерения** , вложенную в развернутый проект.</span><span class="sxs-lookup"><span data-stu-id="046aa-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="046aa-124">Удерживая нажатой клавишу CTRL, щелкните каждое из измерений в папке **Измерения** .</span><span class="sxs-lookup"><span data-stu-id="046aa-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="046aa-125">Щелкните выделенные измерения правой кнопкой мыши и выберите **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="046aa-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="046aa-126">Удерживая нажатой клавишу CTRL, щелкните каждое из измерений в **Списке объектов**.</span><span class="sxs-lookup"><span data-stu-id="046aa-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="046aa-127">Щелкните правой кнопкой мыши выделенные измерения и выберите команду **Обработка. Полная**.</span><span class="sxs-lookup"><span data-stu-id="046aa-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="046aa-128">Для настройки задания пакетной обработки нажмите кнопку **Изменение настроек**.</span><span class="sxs-lookup"><span data-stu-id="046aa-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="046aa-129">В разделе **Параметры обработки**отметьте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="046aa-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="046aa-130">Для параметра**Порядок обработки** выберите **Последовательно**, а параметр **Режим транзакции** выберите **Одна транзакция**.</span><span class="sxs-lookup"><span data-stu-id="046aa-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="046aa-131">**Параметр таблицы обратной записи** установите в значение **Использовать существующие**.</span><span class="sxs-lookup"><span data-stu-id="046aa-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="046aa-132">В разделе **Затронутые объекты**установите флажок **Обработать затронутые объекты** .</span><span class="sxs-lookup"><span data-stu-id="046aa-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="046aa-133">Перейдите на вкладку **ошибки ключа измерения** . Убедитесь, что выбран параметр **использовать конфигурацию ошибок по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="046aa-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="046aa-134">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Изменение настроек** .</span><span class="sxs-lookup"><span data-stu-id="046aa-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="046aa-135">На экране **Обработка объектов** нажмите кнопку **Выполнить** , чтобы начать выполнение задания обработки.</span><span class="sxs-lookup"><span data-stu-id="046aa-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="046aa-136">Когда в поле **Состояние** появится сообщение **Обработка выполнена**, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="046aa-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="046aa-137">Нажмите кнопку **Закрыть** на экране **Обработка объектов** .</span><span class="sxs-lookup"><span data-stu-id="046aa-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="046aa-138">Пакетная обработка с использованием XMLA в Management Studio</span><span class="sxs-lookup"><span data-stu-id="046aa-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="046aa-139">Вы можете создать скрипт XMLA, который выполняет пакетную обработку.</span><span class="sxs-lookup"><span data-stu-id="046aa-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="046aa-140">Сначала создайте скрипт XMLA в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] для каждого объекта, а затем объедините их в один запрос XMLA, который выполняется в интерактивном режиме или в рамках запланированной задачи.</span><span class="sxs-lookup"><span data-stu-id="046aa-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="046aa-141">Пошаговые инструкции см. в **примере 2** в разделе [Планирование административных задач SSAS с помощью агент SQL Server](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span><span class="sxs-lookup"><span data-stu-id="046aa-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046aa-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="046aa-142">See Also</span></span>  
 [<span data-ttu-id="046aa-143">Обработка объектов многомерной модели</span><span class="sxs-lookup"><span data-stu-id="046aa-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
