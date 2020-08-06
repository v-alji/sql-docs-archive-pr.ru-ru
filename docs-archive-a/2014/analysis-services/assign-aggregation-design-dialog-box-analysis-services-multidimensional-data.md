---
title: Диалоговое окно «Назначение статистической схемы» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.copyaggregationdesign.f1
ms.assetid: 50c26cb1-c294-4f17-8b9e-435fdbd4806d
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfc4f7a0847373360a79ddda366ad7aa3f02c5de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656932"
---
# <a name="assign-aggregation-design-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="409d2-102">Диалоговое окно «Назначение статистической схемы» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="409d2-102">Assign Aggregation Design Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="409d2-103">Диалоговое окно **Назначение статистической схемы** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] позволяет присвоить статистические схемы целевым секциям.</span><span class="sxs-lookup"><span data-stu-id="409d2-103">Use the **Assign Aggregation Design** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to assign aggregation designs to one or more destination partitions.</span></span> <span data-ttu-id="409d2-104">Чтобы открыть диалоговое окно **Назначение статистической схемы** , щелкните правой кнопкой мыши секцию или статистическую схему в **обозревателе объектов** и выберите в контекстном меню пункт **Назначение статистической схемы**.</span><span class="sxs-lookup"><span data-stu-id="409d2-104">You can display the **Assign Aggregation Design** dialog box by right-clicking a partition or aggregation design in **Object Explorer** and selecting **Assign Aggregation Design**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="409d2-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="409d2-105">Options</span></span>  
  
|<span data-ttu-id="409d2-106">Термин</span><span class="sxs-lookup"><span data-stu-id="409d2-106">Term</span></span>|<span data-ttu-id="409d2-107">Определение</span><span class="sxs-lookup"><span data-stu-id="409d2-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="409d2-108">**Статистические схемы**</span><span class="sxs-lookup"><span data-stu-id="409d2-108">**Aggregation designs**</span></span>|<span data-ttu-id="409d2-109">Выберите статистическую схему, которую требуется присвоить целевым секциям.</span><span class="sxs-lookup"><span data-stu-id="409d2-109">Select an aggregation design to assign to one or more destination partitions.</span></span>|  
|<span data-ttu-id="409d2-110">**Целевые секции**</span><span class="sxs-lookup"><span data-stu-id="409d2-110">**Destination partitions**</span></span>|<span data-ttu-id="409d2-111">Выберите секции, которым требуется присвоить статистическую схему.</span><span class="sxs-lookup"><span data-stu-id="409d2-111">Select the partitions to which to assign the aggregation design.</span></span> <span data-ttu-id="409d2-112">Для выбора целевых секций используется следующая сетка:</span><span class="sxs-lookup"><span data-stu-id="409d2-112">The following grid is used to specify destination partitions:</span></span><br /><br /> <span data-ttu-id="409d2-113">\<check box>: Установите или снимите флажок в заголовке столбца, чтобы включить или исключить все перечисленные секции в качестве секций назначения.</span><span class="sxs-lookup"><span data-stu-id="409d2-113">\<check box>: Select or clear the check box in the column header to include or exclude all listed partitions as destination partitions.</span></span> <span data-ttu-id="409d2-114">Установите или снимите флажок рядом с секцией, чтобы включить или исключить ее в качестве секции назначения.</span><span class="sxs-lookup"><span data-stu-id="409d2-114">Select or clear a check box next to a partition to include or exclude that partition as a destination partition.</span></span><br /><br /> <span data-ttu-id="409d2-115">**Partition**: отображает имя секции.</span><span class="sxs-lookup"><span data-stu-id="409d2-115">**Partition**: Displays the name of the partition.</span></span><br /><br /> <span data-ttu-id="409d2-116">**Источник**: отображает исходную таблицу или запрос для секции.</span><span class="sxs-lookup"><span data-stu-id="409d2-116">**Source**: Displays the source table or query for the partition.</span></span><br /><br /> <span data-ttu-id="409d2-117">**Статистическая**схема: отображает имя существующей статистической схемы для секции.</span><span class="sxs-lookup"><span data-stu-id="409d2-117">**Aggregation Design**: Displays the name of the existing aggregation design for the partition.</span></span>|  
|<span data-ttu-id="409d2-118">**Позволяет скрыть секции со статистическими схемами**</span><span class="sxs-lookup"><span data-stu-id="409d2-118">**Hide partitions with aggregation designs**</span></span>|<span data-ttu-id="409d2-119">Выберите этот параметр, чтобы вывести на экран только те секции, которым не присвоены никакие статистические схемы.</span><span class="sxs-lookup"><span data-stu-id="409d2-119">Select to show only the partitions that do not have aggregation designs assigned to them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="409d2-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="409d2-120">See Also</span></span>  
 [<span data-ttu-id="409d2-121">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="409d2-121">Aggregations and Aggregation Designs</span></span>](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
