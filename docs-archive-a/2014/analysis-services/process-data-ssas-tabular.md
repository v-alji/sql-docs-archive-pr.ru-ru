---
title: Обработка данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750256"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="6d46f-102">Обработка данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="6d46f-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="6d46f-103">При импорте данных в табличную модель в режиме кэширования создается моментальный снимок данных на момент импорта.</span><span class="sxs-lookup"><span data-stu-id="6d46f-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="6d46f-104">В некоторых случаях эти данные могут оказаться неизменяемыми, и тогда обновлять их в модели не требуется.</span><span class="sxs-lookup"><span data-stu-id="6d46f-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="6d46f-105">Однако с большей вероятностью импортированные данные будут регулярно изменяться, поэтому для того, чтобы модель отражала самые актуальные данные из источников данных, необходимо обрабатывать (обновлять) данные и проводить повторный расчет вычисляемых данных.</span><span class="sxs-lookup"><span data-stu-id="6d46f-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="6d46f-106">Чтобы обновить данные в модели, выполните действие обработки для всех таблиц, для отдельной таблицы, секции или соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="6d46f-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="6d46f-107">Действия процесса при создании проекта модели необходимо инициировать вручную в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d46f-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6d46f-108">После развертывания модели операции процесса можно выполнить с помощью [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или запланировать с помощью скрипта.</span><span class="sxs-lookup"><span data-stu-id="6d46f-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="6d46f-109">Описываемые здесь задачи относятся ко всем действиям процессов, которые можно выполнять во время разработки моделей в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d46f-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6d46f-110">Дополнительные сведения о действиях по обработке для развернутой модели см. в разделе [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d46f-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6d46f-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="6d46f-111">Related Tasks</span></span>  
  
|<span data-ttu-id="6d46f-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="6d46f-112">Topic</span></span>|<span data-ttu-id="6d46f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6d46f-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6d46f-114">Обработка данных вручную (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="6d46f-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="6d46f-115">Описывает обработку данных рабочей области модели вручную.</span><span class="sxs-lookup"><span data-stu-id="6d46f-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="6d46f-116">Устранение неполадок обработки данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="6d46f-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="6d46f-117">Описывает устранение неполадок при операциях обработки.</span><span class="sxs-lookup"><span data-stu-id="6d46f-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
