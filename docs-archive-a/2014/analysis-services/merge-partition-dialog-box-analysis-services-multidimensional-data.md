---
title: Диалоговое окно «слияние секции» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667459"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="a17c5-102">Диалоговое окно «Слияние секций» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="a17c5-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="a17c5-103">Диалоговое окно **Слияние секций** в среде **SQL Server Management Studio** позволяет объединять секции для группы мер в кубе.</span><span class="sxs-lookup"><span data-stu-id="a17c5-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="a17c5-104">Для вывода диалогового окна **Слияние секций** щелкните правой кнопкой мыши папку "Секции" в **обозревателе объектов** и выберите команду **Слияние секций** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="a17c5-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a17c5-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="a17c5-105">Options</span></span>  
 <span data-ttu-id="a17c5-106">**Server**</span><span class="sxs-lookup"><span data-stu-id="a17c5-106">**Server**</span></span>  
 <span data-ttu-id="a17c5-107">Выберите имя экземпляра службы Analysis Services, содержащего нужную секцию.</span><span class="sxs-lookup"><span data-stu-id="a17c5-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="a17c5-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a17c5-108">**Name**</span></span>  
 <span data-ttu-id="a17c5-109">Выберите имя существующей секции для использования в качестве секции назначения.</span><span class="sxs-lookup"><span data-stu-id="a17c5-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="a17c5-110">**Папка**</span><span class="sxs-lookup"><span data-stu-id="a17c5-110">**Folder**</span></span>  
 <span data-ttu-id="a17c5-111">Выводит имя папки, содержащей секцию назначения, если секция, выбранная в поле «Имя», не использует папку, установленную по умолчанию для данного экземпляра служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a17c5-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="a17c5-112">**Исходные секции**</span><span class="sxs-lookup"><span data-stu-id="a17c5-112">**Source Partitions**</span></span>  
 <span data-ttu-id="a17c5-113">Выводит сетку с исходными секциями, которые можно объединить в секцию назначения.</span><span class="sxs-lookup"><span data-stu-id="a17c5-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a17c5-114">Объединять можно только секции в одной группе мер с одной статистической схемой.</span><span class="sxs-lookup"><span data-stu-id="a17c5-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="a17c5-115">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="a17c5-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="a17c5-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="a17c5-116">Column</span></span>|<span data-ttu-id="a17c5-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a17c5-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a17c5-118">**Объединить**</span><span class="sxs-lookup"><span data-stu-id="a17c5-118">**Merge**</span></span>|<span data-ttu-id="a17c5-119">Выберите, чтобы выполнить слияние исходной секции с секцией назначения.</span><span class="sxs-lookup"><span data-stu-id="a17c5-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="a17c5-120">**Имя секции**</span><span class="sxs-lookup"><span data-stu-id="a17c5-120">**Partition Name**</span></span>|<span data-ttu-id="a17c5-121">Отображает имя исходной секции.</span><span class="sxs-lookup"><span data-stu-id="a17c5-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="a17c5-122">**Последняя обработка**</span><span class="sxs-lookup"><span data-stu-id="a17c5-122">**Last Processed**</span></span>|<span data-ttu-id="a17c5-123">Выводит дату и время последней обработки исходной секции.</span><span class="sxs-lookup"><span data-stu-id="a17c5-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a17c5-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a17c5-124">See Also</span></span>  
 <span data-ttu-id="a17c5-125">[Секции &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a17c5-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a17c5-126">Объединение секций в службах Analysis Services (службы SSAS — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="a17c5-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
