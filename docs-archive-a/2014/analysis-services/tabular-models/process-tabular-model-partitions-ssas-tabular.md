---
title: Обработка секций табличной модели (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728754"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="9f2f8-102">Обработка секций табличной модели (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="9f2f8-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="9f2f8-103">Секции разделяют таблицу на логические части.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="9f2f8-104">Каждая секция затем может обрабатываться (обновляться) независимо от других секций.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="9f2f8-105">Приведенные в этом разделе задачи описывают обработку секций в базе данных model с помощью диалогового окна **Обработка секций** в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f2f8-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="9f2f8-106">Обработка секции</span><span class="sxs-lookup"><span data-stu-id="9f2f8-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="9f2f8-107">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши таблицу, в которой есть секции для обработки, и выберите пункт **Секции**.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="9f2f8-108">В диалоговом окне **Секции** на вкладке **Секции**нажмите кнопку «Обработка».</span><span class="sxs-lookup"><span data-stu-id="9f2f8-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="9f2f8-109">В диалоговом окне **Обработка секций** в списке **режим** выберите один из следующих режимов обработки:</span><span class="sxs-lookup"><span data-stu-id="9f2f8-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="9f2f8-110">Режим</span><span class="sxs-lookup"><span data-stu-id="9f2f8-110">Mode</span></span>|<span data-ttu-id="9f2f8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9f2f8-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="9f2f8-112">**Обработка. По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="9f2f8-112">**Process Default**</span></span>|<span data-ttu-id="9f2f8-113">Обнаруживает состояние обработки объекта секции и выполняет обработку, необходимую для перевода необработанных или частично обработанных объектов секции в полностью обработанное состояние.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="9f2f8-114">Выполняется загрузка данных для пустых таблиц и секций; иерархии, вычисляемые столбцы и связи строятся или перестраиваются.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="9f2f8-115">**Обработка. Полная**</span><span class="sxs-lookup"><span data-stu-id="9f2f8-115">**Process Full**</span></span>|<span data-ttu-id="9f2f8-116">Обрабатывает объект секций и все объекты, которые в нем содержатся.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="9f2f8-117">Если объект, который обрабатывается методом полной обработки, уже был обработан, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] удаляют все данные объекта, а затем обрабатывают его.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="9f2f8-118">Этот тип обработки требуется при внесении структурных изменений в объект.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="9f2f8-119">**Обработка данных**</span><span class="sxs-lookup"><span data-stu-id="9f2f8-119">**Process Data**</span></span>|<span data-ttu-id="9f2f8-120">Выполняется загрузка данных в секцию или таблицу без перестроения иерархий или связей или повторного вычисления вычисленных столбцов и мер.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="9f2f8-121">**Обработка с очисткой**</span><span class="sxs-lookup"><span data-stu-id="9f2f8-121">**Process Clear**</span></span>|<span data-ttu-id="9f2f8-122">Удаляет все данные из секции.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="9f2f8-123">**Обработка с добавлением**</span><span class="sxs-lookup"><span data-stu-id="9f2f8-123">**Process Add**</span></span>|<span data-ttu-id="9f2f8-124">Постепенно обновляет секцию с включением новых данных.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="9f2f8-125">В столбце флажков **Обработка** выберите секции для обработки в текущем режиме и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9f2f8-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2f8-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f2f8-126">See Also</span></span>  
 <span data-ttu-id="9f2f8-127">[Секции табличной модели &#40;табличные&#41;SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9f2f8-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="9f2f8-128">Создание секций табличной модели и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="9f2f8-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
