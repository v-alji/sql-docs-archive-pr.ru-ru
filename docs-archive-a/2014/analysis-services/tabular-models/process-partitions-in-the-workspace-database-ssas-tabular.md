---
title: Обработка секций в базе данных рабочей области (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3a369705-43fa-4961-9045-32e06fbdde33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4a996e90b30794882535327ea3192d7e72818422
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728761"
---
# <a name="process-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="f247f-102">Обработка секций в базе данных рабочей области (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="f247f-102">Process Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="f247f-103">Секции разделяют таблицу на логические части.</span><span class="sxs-lookup"><span data-stu-id="f247f-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="f247f-104">Каждая секция затем может обрабатываться (обновляться) независимо от других секций.</span><span class="sxs-lookup"><span data-stu-id="f247f-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="f247f-105">Приведенные в этом разделе задачи описывают обработку секций в базе данных рабочей области модели с помощью диалогового окна **Обработка секций** в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f247f-105">The tasks in this topic describe how to process partitions in the model workspace database by using the **Process Partitions** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f247f-106">После развертывания модели в другом экземпляре служб Analysis Services администраторы баз данных могут создавать секции и управлять ими в (развернутой) модели с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], скриптов или пакета служб IS.</span><span class="sxs-lookup"><span data-stu-id="f247f-106">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], by script, or by using an IS package.</span></span> <span data-ttu-id="f247f-107">Дополнительные сведения см. в разделе [Создание секций табличной модели и управление ими (табличные службы SSAS)](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f247f-107">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="f247f-108">Обработка секции</span><span class="sxs-lookup"><span data-stu-id="f247f-108">To process a partition</span></span>  
  
1.  <span data-ttu-id="f247f-109">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]выберите в меню **Модель** пункт **Обработать** (Обновить), а затем пункт **Обработать секции**.</span><span class="sxs-lookup"><span data-stu-id="f247f-109">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="f247f-110">В списке **Режим** выберите один из следующих режимов обработки:</span><span class="sxs-lookup"><span data-stu-id="f247f-110">In the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="f247f-111">Режим</span><span class="sxs-lookup"><span data-stu-id="f247f-111">Mode</span></span>|<span data-ttu-id="f247f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f247f-112">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="f247f-113">**Обработка. По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="f247f-113">**Process Default**</span></span>|<span data-ttu-id="f247f-114">Обнаруживает состояние обработки объекта секции и выполняет обработку, необходимую для перевода необработанных или частично обработанных объектов секции в полностью обработанное состояние.</span><span class="sxs-lookup"><span data-stu-id="f247f-114">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="f247f-115">Выполняется загрузка данных для пустых таблиц и секций; иерархии, вычисляемые столбцы и связи строятся или перестраиваются.</span><span class="sxs-lookup"><span data-stu-id="f247f-115">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="f247f-116">**Обработка. Полная**</span><span class="sxs-lookup"><span data-stu-id="f247f-116">**Process Full**</span></span>|<span data-ttu-id="f247f-117">Обрабатывает объект секций и все объекты, которые в нем содержатся.</span><span class="sxs-lookup"><span data-stu-id="f247f-117">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="f247f-118">Если объект, который обрабатывается методом полной обработки, уже был обработан, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] удаляют все данные объекта, а затем обрабатывают его.</span><span class="sxs-lookup"><span data-stu-id="f247f-118">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="f247f-119">Этот тип обработки требуется при внесении структурных изменений в объект.</span><span class="sxs-lookup"><span data-stu-id="f247f-119">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="f247f-120">**Обработка данных**</span><span class="sxs-lookup"><span data-stu-id="f247f-120">**Process Data**</span></span>|<span data-ttu-id="f247f-121">Выполняется загрузка данных в секцию или таблицу без перестроения иерархий или связей или повторного вычисления вычисленных столбцов и мер.</span><span class="sxs-lookup"><span data-stu-id="f247f-121">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="f247f-122">**Обработка с очисткой**</span><span class="sxs-lookup"><span data-stu-id="f247f-122">**Process Clear**</span></span>|<span data-ttu-id="f247f-123">Удаляет все данные из секции.</span><span class="sxs-lookup"><span data-stu-id="f247f-123">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="f247f-124">**Обработка с добавлением**</span><span class="sxs-lookup"><span data-stu-id="f247f-124">**Process Add**</span></span>|<span data-ttu-id="f247f-125">Постепенно обновляет секцию с включением новых данных.</span><span class="sxs-lookup"><span data-stu-id="f247f-125">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="f247f-126">В столбце флажков **Обработка** выберите секции для обработки в текущем режиме и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f247f-126">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f247f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f247f-127">See Also</span></span>  
 <span data-ttu-id="f247f-128">[Секции &#40;табличные&#41;SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f247f-128">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f247f-129">Создание секций и управление ими в базе данных рабочей области (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="f247f-129">Create and Manage Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](workspace-database-ssas-tabular.md)  
  
  
