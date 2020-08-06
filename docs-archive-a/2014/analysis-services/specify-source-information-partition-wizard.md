---
title: Определение исходных сведений (мастер секционирования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666766"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="f6998-102">Определение исходных сведений (мастер секционирования)</span><span class="sxs-lookup"><span data-stu-id="f6998-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="f6998-103">С помощью страницы **Определение исходных сведений** можно выбрать группу мер, в которой создается секция, а также представление источника данных, и отфильтровать таблицы для секции.</span><span class="sxs-lookup"><span data-stu-id="f6998-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f6998-104">Если из списка **Доступные таблицы** выбирается таблица, которая используется другой секцией, необходимо предоставить запрос на странице **Ограничение на строки** , иначе возникнет риск повторения данных в кубе.</span><span class="sxs-lookup"><span data-stu-id="f6998-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f6998-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="f6998-105">Options</span></span>  
 <span data-ttu-id="f6998-106">**Группа мер**</span><span class="sxs-lookup"><span data-stu-id="f6998-106">**Measure group**</span></span>  
 <span data-ttu-id="f6998-107">Выберите группу мер для этой секции.</span><span class="sxs-lookup"><span data-stu-id="f6998-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="f6998-108">**Искать в:**</span><span class="sxs-lookup"><span data-stu-id="f6998-108">**Look in**</span></span>  
 <span data-ttu-id="f6998-109">Выберите источник данных или представление источника данных, содержащие исходные таблицы для этой секции.</span><span class="sxs-lookup"><span data-stu-id="f6998-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="f6998-110">По умолчанию выбирается представление источника данных, используемое группой мер.</span><span class="sxs-lookup"><span data-stu-id="f6998-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="f6998-111">**Фильтровать таблицы**</span><span class="sxs-lookup"><span data-stu-id="f6998-111">**Filter tables**</span></span>  
 <span data-ttu-id="f6998-112">Введите строку, которая будет использоваться для ограничения имен таблиц, отображаемых в списке **Доступные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="f6998-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="f6998-113">**Поиск таблиц**</span><span class="sxs-lookup"><span data-stu-id="f6998-113">**Find tables**</span></span>  
 <span data-ttu-id="f6998-114">Выберите, чтобы обновить список таблиц **Доступные таблицы**, еще более ограничивая его, если в поле **Фильтровать таблицы**введено значение.</span><span class="sxs-lookup"><span data-stu-id="f6998-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="f6998-115">**Доступные таблицы**</span><span class="sxs-lookup"><span data-stu-id="f6998-115">**Available tables**</span></span>  
 <span data-ttu-id="f6998-116">Выбор таблиц, используемых в качестве исходных таблиц для секционирования.</span><span class="sxs-lookup"><span data-stu-id="f6998-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="f6998-117">**Мастер секционирования** создает одну секцию для каждой таблицы, выбранной из списка **Доступные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="f6998-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="f6998-118">Если в поле **Фильтровать таблицы**не задан фильтр, этот список будет содержать все таблицы из источника данных или представления источников данных, определенного параметром **Искать в** , а также таблицы, аналогичные по структуре таблице фактов, используемой группой мер, определенной параметром **Группа мер**.</span><span class="sxs-lookup"><span data-stu-id="f6998-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="f6998-119">Если в поле **Фильтровать таблицы**указан фильтр, список еще более ограничивается в результате сравнения фильтра с именами таблиц, удовлетворяющими предыдущему критерию.</span><span class="sxs-lookup"><span data-stu-id="f6998-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="f6998-120">Отображаются только те таблицы, которые содержат строку, указанную в поле **Фильтровать таблицы** .</span><span class="sxs-lookup"><span data-stu-id="f6998-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6998-121">Если выбирается несколько таблиц, страницу **Ограничение на строки** невозможно отобразить, и нельзя ограничить строки для секций, созданных из выбранных таблиц.</span><span class="sxs-lookup"><span data-stu-id="f6998-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="f6998-122">Для ограничения строк во всех секциях мастер секционирования должен выполняться по одному разу для каждой таблицы, из которых должна создаваться секция.</span><span class="sxs-lookup"><span data-stu-id="f6998-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6998-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6998-123">See Also</span></span>  
 [<span data-ttu-id="f6998-124">Секции (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="f6998-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
