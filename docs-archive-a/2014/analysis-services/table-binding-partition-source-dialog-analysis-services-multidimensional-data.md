---
title: Сведения о привязке таблицы (диалоговое окно «Источник секции») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658432"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b3741-102">Сведения о привязке таблицы (диалоговое окно «Источник секции») (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="b3741-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b3741-103">Используйте параметр **Привязка таблицы** в диалоговом окне **Источник секции** , чтобы указать таблицу фактов, предоставляющую данные для этой секции.</span><span class="sxs-lookup"><span data-stu-id="b3741-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="b3741-104">Чтобы открыть эту панель, выберите **Привязка таблицы** в параметре **Тип привязки** в диалоговом окне **Источник секции** .</span><span class="sxs-lookup"><span data-stu-id="b3741-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3741-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="b3741-105">Options</span></span>  
 <span data-ttu-id="b3741-106">**Группа мер**</span><span class="sxs-lookup"><span data-stu-id="b3741-106">**Measure group**</span></span>  
 <span data-ttu-id="b3741-107">Отображает группу мер для этой секции.</span><span class="sxs-lookup"><span data-stu-id="b3741-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="b3741-108">**Искать в:**</span><span class="sxs-lookup"><span data-stu-id="b3741-108">**Look in**</span></span>  
 <span data-ttu-id="b3741-109">Выберите источник данных или представление источника данных, содержащие исходные таблицы для этой секции.</span><span class="sxs-lookup"><span data-stu-id="b3741-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="b3741-110">Представление источника данных, используемое выбранной группой мер, выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b3741-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="b3741-111">**Фильтровать таблицы**</span><span class="sxs-lookup"><span data-stu-id="b3741-111">**Filter tables**</span></span>  
 <span data-ttu-id="b3741-112">Введите строку, которая будет использоваться для ограничения имен таблиц, отображаемых в списке **Доступные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="b3741-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="b3741-113">**Поиск таблиц**</span><span class="sxs-lookup"><span data-stu-id="b3741-113">**Find tables**</span></span>  
 <span data-ttu-id="b3741-114">Выберите, чтобы обновить список таблиц **Доступные таблицы**, еще более ограничивая его, если в поле **Фильтровать таблицы**введено значение.</span><span class="sxs-lookup"><span data-stu-id="b3741-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="b3741-115">**Доступные таблицы**</span><span class="sxs-lookup"><span data-stu-id="b3741-115">**Available tables**</span></span>  
 <span data-ttu-id="b3741-116">Щелкните, чтобы выбрать таблицу в качестве исходной таблицы для секции.</span><span class="sxs-lookup"><span data-stu-id="b3741-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="b3741-117">Если в поле **Фильтровать таблицы**не указан фильтр, то выводится список всех таблиц в источнике данных или представлении источника данных, указанном в поле **Искать в** , структура которых сходна со структурой таблицы фактов, используемой группой мер, обозначенной в поле **Группа мер** .</span><span class="sxs-lookup"><span data-stu-id="b3741-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="b3741-118">Если в поле **Фильтровать таблицы**указан фильтр, то список ограничивается путем сравнения фильтра с именами таблиц, которые соответствуют приведенным выше критериям.</span><span class="sxs-lookup"><span data-stu-id="b3741-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="b3741-119">Отображаются только те таблицы, которые содержат строку, указанную в поле **Фильтровать таблицы** .</span><span class="sxs-lookup"><span data-stu-id="b3741-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3741-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3741-120">See Also</span></span>  
 [<span data-ttu-id="b3741-121">Диалоговое окно «Источник секции» &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b3741-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
