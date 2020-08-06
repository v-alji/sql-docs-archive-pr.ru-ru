---
title: Выбор таблиц и представлений (мастер представлений источников данных) (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738885"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="b9094-102">Выбор таблиц и представлений (мастер представлений источников данных) (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b9094-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="b9094-103">Используйте страницу **Выбор таблиц и представлений** для выбора таблиц или представлений из источника данных, которые нужно включить в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="b9094-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9094-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="b9094-104">Options</span></span>  
 <span data-ttu-id="b9094-105">**Available objects**</span><span class="sxs-lookup"><span data-stu-id="b9094-105">**Available objects**</span></span>  
 <span data-ttu-id="b9094-106">Содержит таблицы и представления в схеме источника данных.</span><span class="sxs-lookup"><span data-stu-id="b9094-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="b9094-107">Перед именем каждого объекта добавляется префикс с именем схемы, если в списке представлено более одной схемы.</span><span class="sxs-lookup"><span data-stu-id="b9094-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="b9094-108">Если в списке представлена только одна схема, то префикс с именем схемы не используется перед именами объектов.</span><span class="sxs-lookup"><span data-stu-id="b9094-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="b9094-109">Чтобы упорядочить список в порядке возрастания или убывания, щелкните **Имя** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="b9094-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="b9094-110">**Included objects**</span><span class="sxs-lookup"><span data-stu-id="b9094-110">**Included objects**</span></span>  
 <span data-ttu-id="b9094-111">Содержит таблицы и представления, включенные в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="b9094-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="b9094-112">Чтобы упорядочить список в порядке возрастания или убывания, щелкните **Имя** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="b9094-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="b9094-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="b9094-113">**Filter**</span></span>  
 <span data-ttu-id="b9094-114">Фильтрует объекты, представленные в списке **Доступные объекты**.</span><span class="sxs-lookup"><span data-stu-id="b9094-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="b9094-115">Введите строку, а затем нажмите **Фильтр** для отображения в списке только тех имен, которые содержат введенную строку.</span><span class="sxs-lookup"><span data-stu-id="b9094-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="b9094-116">Чтобы выполнить точный поиск только заданной строки, заключите строку в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b9094-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="b9094-117">Фильтр не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="b9094-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="b9094-118">Символы-шаблоны, приведенные в следующей таблице, можно вставлять в любом месте строки фильтра.</span><span class="sxs-lookup"><span data-stu-id="b9094-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="b9094-119">Символ-шаблон</span><span class="sxs-lookup"><span data-stu-id="b9094-119">Wildcard character</span></span>|<span data-ttu-id="b9094-120">Значение</span><span class="sxs-lookup"><span data-stu-id="b9094-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="b9094-121">Любая строка символов</span><span class="sxs-lookup"><span data-stu-id="b9094-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="b9094-122">Любая строка символов</span><span class="sxs-lookup"><span data-stu-id="b9094-122">Any string of characters</span></span>|  
|<span data-ttu-id="b9094-123">**?**</span><span class="sxs-lookup"><span data-stu-id="b9094-123">**?**</span></span>|<span data-ttu-id="b9094-124">Любой одиночный символ</span><span class="sxs-lookup"><span data-stu-id="b9094-124">A single character</span></span>|  
|<span data-ttu-id="b9094-125">**"** *строка* **"**</span><span class="sxs-lookup"><span data-stu-id="b9094-125">**"** *string* **"**</span></span>|<span data-ttu-id="b9094-126">Постоянная строка символов.</span><span class="sxs-lookup"><span data-stu-id="b9094-126">A literal string of characters.</span></span> <span data-ttu-id="b9094-127">Этот символ-шаблон соответствует любой подстроке внутри имени объекта.</span><span class="sxs-lookup"><span data-stu-id="b9094-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="b9094-128">**Show system objects**</span><span class="sxs-lookup"><span data-stu-id="b9094-128">**Show system objects**</span></span>  
 <span data-ttu-id="b9094-129">Отображает системные объекты в списке **Доступные объекты**.</span><span class="sxs-lookup"><span data-stu-id="b9094-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="b9094-130">Этот параметр доступен, только если поставщик источников данных предоставляет системные объекты.</span><span class="sxs-lookup"><span data-stu-id="b9094-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="b9094-131">Удаление системных объектов из списка **Включенные объекты** автоматически устанавливает этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b9094-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="b9094-132">**Add related tables**</span><span class="sxs-lookup"><span data-stu-id="b9094-132">**Add related tables**</span></span>  
 <span data-ttu-id="b9094-133">Добавление всех таблиц, связанных с теми, которые находятся в списке **Включенные объекты**.</span><span class="sxs-lookup"><span data-stu-id="b9094-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="b9094-134">Этот параметр не добавляет представления.</span><span class="sxs-lookup"><span data-stu-id="b9094-134">This option does not add views.</span></span> <span data-ttu-id="b9094-135">Однако добавляются все секционированные таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9094-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="b9094-136">Если выбран критерий соответствия имен на странице **Совпадение имен** мастера, этот параметр также включит логически связанные таблицы согласно выбранному критерию.</span><span class="sxs-lookup"><span data-stu-id="b9094-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="b9094-137">Таблицы также будут включены, если они относятся к только что добавленным связанным таблицам и если они имеют структуру, идентичную структуре исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="b9094-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9094-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9094-138">See Also</span></span>  
 <span data-ttu-id="b9094-139">[Справка F1 мастера представлений источников данных &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b9094-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="b9094-140">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="b9094-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
