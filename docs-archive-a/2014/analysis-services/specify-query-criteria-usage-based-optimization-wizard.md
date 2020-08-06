---
title: Определение критериев запроса (мастер оптимизации с учетом использования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657332"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="202d4-102">Определение критериев запросов (мастер оптимизации с учетом использования)</span><span class="sxs-lookup"><span data-stu-id="202d4-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="202d4-103">На странице **Определение критериев запроса** выберите один или несколько параметров фильтрации, чтобы определить запросы, которые следует оптимизировать.</span><span class="sxs-lookup"><span data-stu-id="202d4-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d4-104">Эта страница отключена, если служба [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] не может подключиться к журналу запросов.</span><span class="sxs-lookup"><span data-stu-id="202d4-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="202d4-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="202d4-105">Options</span></span>  
 <span data-ttu-id="202d4-106">**Статистика журнала запросов**</span><span class="sxs-lookup"><span data-stu-id="202d4-106">**Query log statistics**</span></span>  
 <span data-ttu-id="202d4-107">Отображает данные о запросах, хранимых в журнале запросов для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="202d4-108">Отображаются следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="202d4-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="202d4-109">Термин</span><span class="sxs-lookup"><span data-stu-id="202d4-109">Term</span></span>|<span data-ttu-id="202d4-110">Определение</span><span class="sxs-lookup"><span data-stu-id="202d4-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="202d4-111">**Всего запросов**</span><span class="sxs-lookup"><span data-stu-id="202d4-111">**Total queries**</span></span>|<span data-ttu-id="202d4-112">Отображает суммарное количество запросов, хранимых в журнале запросов для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="202d4-113">**Уникальные запросы**</span><span class="sxs-lookup"><span data-stu-id="202d4-113">**Distinct queries**</span></span>|<span data-ttu-id="202d4-114">Отображает количество уникальных запросов, хранимых в журнале запросов для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="202d4-115">**Уникальные пользователи**</span><span class="sxs-lookup"><span data-stu-id="202d4-115">**Distinct users**</span></span>|<span data-ttu-id="202d4-116">Отображает суммарное количество уникальных пользователей, связанных с запросами, хранимыми в журнале запросов для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="202d4-117">**Среднее время отклика**</span><span class="sxs-lookup"><span data-stu-id="202d4-117">**Average response time**</span></span>|<span data-ttu-id="202d4-118">Отображает среднее время отклика для запросов, хранимых в журнале запросов для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="202d4-119">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="202d4-119">**Beginning date**</span></span>  
 <span data-ttu-id="202d4-120">Фильтрует запросы в журнале запросов на основе даты и времени начала.</span><span class="sxs-lookup"><span data-stu-id="202d4-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="202d4-121">Выберите или введите дату в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="202d4-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d4-122"> Если параметр **Дата окончания** не выбран, то рассматриваются все запросы в журнале запросов на дату и время, заданные для данного параметра или после них.</span><span class="sxs-lookup"><span data-stu-id="202d4-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="202d4-123">**Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="202d4-123">**Ending date**</span></span>  
 <span data-ttu-id="202d4-124">Фильтрует запросы в журнале запросов на основе даты и времени окончания.</span><span class="sxs-lookup"><span data-stu-id="202d4-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="202d4-125">Выберите или введите дату в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="202d4-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d4-126"> Если параметр **Дата начала** не выбран, то рассматриваются все запросы в журнале запросов на дату и время, заданные для данного параметра или до них.</span><span class="sxs-lookup"><span data-stu-id="202d4-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="202d4-127">**Пользователи**</span><span class="sxs-lookup"><span data-stu-id="202d4-127">**Users**</span></span>  
 <span data-ttu-id="202d4-128">Фильтрует запросы в журнале запросов на основе заданного набора пользователей.</span><span class="sxs-lookup"><span data-stu-id="202d4-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="202d4-129">Нажмите кнопку с многоточием (**...**) для отображения диалогового окна **Выбор пользователей** и выберите пользователей, по которым необходимо фильтровать запросы.</span><span class="sxs-lookup"><span data-stu-id="202d4-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="202d4-130">Дополнительные сведения о диалоговом окне **Выбор пользователей** см. в разделе [Диалоговое окно "Выбор пользователей" (службы Analysis Services — многомерные данные)](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="202d4-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="202d4-131">**Наиболее часто выполняемые запросы**</span><span class="sxs-lookup"><span data-stu-id="202d4-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="202d4-132">Фильтрует запросы в журнале запросов на основе наибольшего процентного количества уникальных запросов, выполняемых наиболее часто для выбранных секций.</span><span class="sxs-lookup"><span data-stu-id="202d4-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="202d4-133">Выберите или введите процентное значение в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="202d4-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="202d4-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="202d4-134">See Also</span></span>  
 <span data-ttu-id="202d4-135">[Справка F1 мастера оптимизации с учетом использования](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="202d4-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="202d4-136">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="202d4-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
