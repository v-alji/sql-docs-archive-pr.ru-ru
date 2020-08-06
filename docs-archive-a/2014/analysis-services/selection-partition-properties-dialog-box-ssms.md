---
title: Выбор (диалоговое окно «Свойства секции») (SSMS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.partitionproperties.selection.f1
ms.assetid: 29a7b556-2484-4f66-b74c-1c061b3ce25c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c88ebf6beb5e548fc91155bad6ca6d818ce99463
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656602"
---
# <a name="selection-partition-properties-dialog-box-ssms"></a><span data-ttu-id="ba0cd-102">Выбор (диалоговое окно «Свойства секции») (среда SSMS)</span><span class="sxs-lookup"><span data-stu-id="ba0cd-102">Selection (Partition Properties Dialog Box) (SSMS)</span></span>
  <span data-ttu-id="ba0cd-103">Используйте страницу **Выбор** диалогового окна **Свойства секции** в среде SQL Server Management Studio для выбора секции из группы мер, свойства которой на панели **Общие**, **Упреждающее кэширование**или **Конфигурация ошибок** необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-103">Use the **Selection** page of the **Partition Properties** dialog box in SQL Server Management Studio to select a partition from a measure group for which to view or modify properties in the **General**, **Proactive Caching**, or **Error Configuration** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba0cd-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="ba0cd-104">Options</span></span>  
 <span data-ttu-id="ba0cd-105">**Сетка**</span><span class="sxs-lookup"><span data-stu-id="ba0cd-105">**Grid**</span></span>  
 <span data-ttu-id="ba0cd-106">Отображает секцию группы мер, которая содержит выбранную секцию.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-106">Displays the partitions of the measure group that contain the selected partition.</span></span>  
  
 <span data-ttu-id="ba0cd-107">Выберите секцию, свойства которой на панели **Общие**, **Упреждающее кэширование**или **Конфигурация ошибок** необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-107">Select the partition for which to view the properties in the **General**, **Proactive Caching**, or **Error Configuration** page.</span></span>  
  
 <span data-ttu-id="ba0cd-108">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="ba0cd-108">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="ba0cd-109">Столбец</span><span class="sxs-lookup"><span data-stu-id="ba0cd-109">Column</span></span>|<span data-ttu-id="ba0cd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ba0cd-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ba0cd-111">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ba0cd-111">**Name**</span></span>|<span data-ttu-id="ba0cd-112">Отображает имя секции.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-112">Displays the name of the partition.</span></span>|  
|<span data-ttu-id="ba0cd-113">**Source**</span><span class="sxs-lookup"><span data-stu-id="ba0cd-113">**Source**</span></span>|<span data-ttu-id="ba0cd-114">Отображает таблицу или запрос, являющийся источником данных для секции.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-114">Displays the table or query used to provide source data for the partition.</span></span>|  
|<span data-ttu-id="ba0cd-115">**Агрегации**</span><span class="sxs-lookup"><span data-stu-id="ba0cd-115">**Aggregations**</span></span>|<span data-ttu-id="ba0cd-116">Отображает строку с описанием агрегата, используемого секцией.</span><span class="sxs-lookup"><span data-stu-id="ba0cd-116">Displays a string describing the aggregation design used by the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba0cd-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba0cd-117">See Also</span></span>  
 <span data-ttu-id="ba0cd-118">[Диалоговое окно «Свойства секции» &#40;SSMS&#41;](partition-properties-dialog-box-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="ba0cd-118">[Partition Properties Dialog Box &#40;SSMS&#41;](partition-properties-dialog-box-ssms.md) </span></span>  
 <span data-ttu-id="ba0cd-119">[Диалоговое окно "Общие &#40;свойства секции"&#41; &#40;SSMS&#41;](general-partition-properties-dialog-box-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="ba0cd-119">[General &#40;Partition Properties Dialog Box&#41; &#40;SSMS&#41;](general-partition-properties-dialog-box-ssms.md) </span></span>  
 <span data-ttu-id="ba0cd-120">[Упреждающее кэширование &#40;диалоговое окно "Свойства секции"&#41; &#40;SSMS&#41;](proactive-caching-partition-properties-dialog-box-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="ba0cd-120">[Proactive Caching &#40;Partition Properties Dialog Box&#41; &#40;SSMS&#41;](proactive-caching-partition-properties-dialog-box-ssms.md) </span></span>  
 [<span data-ttu-id="ba0cd-121">Конфигурация ошибок при обработке кубов, секций и измерений &#40;SSAS — многомерные&#41;</span><span class="sxs-lookup"><span data-stu-id="ba0cd-121">Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md)  
  
  
