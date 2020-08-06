---
title: Завершение работы мастера (мастер секционирования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656760"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="18fd0-102">Завершение работы мастера (мастер секционирования)</span><span class="sxs-lookup"><span data-stu-id="18fd0-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="18fd0-103">Используйте страницу **Завершение работы мастера** , чтобы дать имя секции, определить статистическую схему для секции и, по желанию, развернуть и обработать секцию после завершения работы мастера секционирования.</span><span class="sxs-lookup"><span data-stu-id="18fd0-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="18fd0-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="18fd0-104">Options</span></span>  
 <span data-ttu-id="18fd0-105">**имя**;</span><span class="sxs-lookup"><span data-stu-id="18fd0-105">**Name**</span></span>  
 <span data-ttu-id="18fd0-106">Введите имя для новой секции.</span><span class="sxs-lookup"><span data-stu-id="18fd0-106">Type the name for the new partition.</span></span> <span data-ttu-id="18fd0-107">При работе с несколькими таблицами введите префикс, который будет добавляться к имени таблицы для создания имени каждой секции.</span><span class="sxs-lookup"><span data-stu-id="18fd0-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="18fd0-108">**Параметры статистической обработки**</span><span class="sxs-lookup"><span data-stu-id="18fd0-108">**Aggregation options**</span></span>  
 <span data-ttu-id="18fd0-109">Указывает параметр статистической обработки для секции.</span><span class="sxs-lookup"><span data-stu-id="18fd0-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="18fd0-110">В следующей таблице перечислены доступные параметры статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="18fd0-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="18fd0-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="18fd0-111">Option</span></span>|<span data-ttu-id="18fd0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="18fd0-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="18fd0-113">**Создать статистические схемы для секции сейчас**</span><span class="sxs-lookup"><span data-stu-id="18fd0-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="18fd0-114">Создает статистические схемы для новой секции сразу после создания новой секции мастером секционирования.</span><span class="sxs-lookup"><span data-stu-id="18fd0-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="18fd0-115">В случае выбора этого параметра мастер статистических схем будет запущен сразу после нажатия кнопки **Готово** в мастере секционирования.</span><span class="sxs-lookup"><span data-stu-id="18fd0-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="18fd0-116">Дополнительные сведения о Мастере статистических схем см. в разделе [Справка F1 мастера статистических схем](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="18fd0-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="18fd0-117">**Создать статистические схемы позже**</span><span class="sxs-lookup"><span data-stu-id="18fd0-117">**Design the aggregations later**</span></span>|<span data-ttu-id="18fd0-118">Создает секцию без проектирования статистических схем на данный момент.</span><span class="sxs-lookup"><span data-stu-id="18fd0-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="18fd0-119">**Копировать статистическую схему из существующей секции**</span><span class="sxs-lookup"><span data-stu-id="18fd0-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="18fd0-120">Копирует статистическую схему из существующей секции в группе мер в новую секцию.</span><span class="sxs-lookup"><span data-stu-id="18fd0-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="18fd0-121">Выбор этого параметра делает доступным параметр **Копировать из** .</span><span class="sxs-lookup"><span data-stu-id="18fd0-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="18fd0-122">Используйте параметр **Копировать из** для выбора секции, из которой нужно скопировать статистическую схему.</span><span class="sxs-lookup"><span data-stu-id="18fd0-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="18fd0-123">Обратите внимание, что секции, которые могут быть объединены в будущем, должны иметь одну и ту же структуру таблицы и статистическую схему.</span><span class="sxs-lookup"><span data-stu-id="18fd0-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="18fd0-124">Если предполагается возможность слияния новой секции с существующей секций в группе мер, следует скопировать статистическую схему из существующей секции в новую секцию.</span><span class="sxs-lookup"><span data-stu-id="18fd0-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="18fd0-125">**Развернуть и обработать сейчас**</span><span class="sxs-lookup"><span data-stu-id="18fd0-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="18fd0-126">Развертывает и обрабатывает секцию в экземпляре служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , указанном на странице **Определение мест обработки и хранения** .</span><span class="sxs-lookup"><span data-stu-id="18fd0-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="18fd0-127">Мастер развертывает и обрабатывает секцию после нажатия кнопки **Готово** на этой странице.</span><span class="sxs-lookup"><span data-stu-id="18fd0-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18fd0-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="18fd0-128">See Also</span></span>  
 [<span data-ttu-id="18fd0-129">Секции (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="18fd0-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
