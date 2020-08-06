---
title: Выбор календарей (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665141"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="0ca19-102">Выбор календарей (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="0ca19-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="0ca19-103">Используйте страницу **Выбор календарей** для создания дополнительных иерархий, представляющих финансовые, отчетные, производственные календари или календари ISO 8601 Организации международных стандартов (ISO) для измерения времени.</span><span class="sxs-lookup"><span data-stu-id="0ca19-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-104"> Данная страница появляется только в случае выбора пункта **Серверное измерение времени** на странице **Выбор типа измерения** либо если было выбрано **Построить измерение без использования источника данных** на странице **Определение измерения** и выбрано **Измерение времени** на странице **Выбор типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ca19-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="0ca19-105">Options</span></span>  
 <span data-ttu-id="0ca19-106">**Финансовый календарь**</span><span class="sxs-lookup"><span data-stu-id="0ca19-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="0ca19-107">Выберите этот параметр для создания иерархии времени на основе финансового календаря.</span><span class="sxs-lookup"><span data-stu-id="0ca19-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="0ca19-108">**День и месяц начала**</span><span class="sxs-lookup"><span data-stu-id="0ca19-108">**Start day and month**</span></span>  
 <span data-ttu-id="0ca19-109">Выберите день и месяц начала финансового календаря.</span><span class="sxs-lookup"><span data-stu-id="0ca19-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-110"> Этот параметр доступен только тогда, когда выбран пункт **Финансовый календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-111">**Принятая схема именования финансового календаря**</span><span class="sxs-lookup"><span data-stu-id="0ca19-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="0ca19-112">Выберите схему именования, которая используется финансовым календарем.</span><span class="sxs-lookup"><span data-stu-id="0ca19-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="0ca19-113">Выберите **Имя календарного года** или **Имя календарного года +1**.</span><span class="sxs-lookup"><span data-stu-id="0ca19-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-114"> Этот параметр доступен только тогда, когда выбран пункт **Финансовый календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-115">**Отчетный (маркетинговый) календарь**</span><span class="sxs-lookup"><span data-stu-id="0ca19-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="0ca19-116">Выбрать этот параметр для создания иерархии времени на основе календаря отчетности.</span><span class="sxs-lookup"><span data-stu-id="0ca19-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="0ca19-117">**Неделя и месяц начала**</span><span class="sxs-lookup"><span data-stu-id="0ca19-117">**Start week and month**</span></span>  
 <span data-ttu-id="0ca19-118">Выберите неделю и месяц начала календаря отчетности.</span><span class="sxs-lookup"><span data-stu-id="0ca19-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-119">Этот параметр доступен только тогда, когда выбран пункт **Отчетный (маркетинговый) календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-120">**Шаблон недель и месяцев**</span><span class="sxs-lookup"><span data-stu-id="0ca19-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="0ca19-121">Выберите шаблон недель и месяцев, используемый календарем отчетности.</span><span class="sxs-lookup"><span data-stu-id="0ca19-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-122">Этот параметр доступен только тогда, когда выбран пункт **Отчетный (маркетинговый) календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-123">В ниже следующей таблице приводятся параметры, доступные для шаблона недель и месяцев.</span><span class="sxs-lookup"><span data-stu-id="0ca19-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="0ca19-124">Значение</span><span class="sxs-lookup"><span data-stu-id="0ca19-124">Value</span></span>|<span data-ttu-id="0ca19-125">Описание</span><span class="sxs-lookup"><span data-stu-id="0ca19-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ca19-126">**Неделя 445**</span><span class="sxs-lookup"><span data-stu-id="0ca19-126">**Week 445**</span></span>|<span data-ttu-id="0ca19-127">Первый месяц квартала включает 4 недели, второй месяц квартала включает 4 недели, а третий месяц квартала включает 5 недель.</span><span class="sxs-lookup"><span data-stu-id="0ca19-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="0ca19-128">**Неделя 454**</span><span class="sxs-lookup"><span data-stu-id="0ca19-128">**Week 454**</span></span>|<span data-ttu-id="0ca19-129">Первый месяц квартала включает 4 недели, второй месяц квартала включает 5 недель, а третий месяц квартала включает 4 недели.</span><span class="sxs-lookup"><span data-stu-id="0ca19-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="0ca19-130">**Неделя 544**</span><span class="sxs-lookup"><span data-stu-id="0ca19-130">**Week 544**</span></span>|<span data-ttu-id="0ca19-131">Первый месяц квартала включает 5 недель, второй месяц квартала включает 4 недели, и третий месяц квартала включает 4 недели.</span><span class="sxs-lookup"><span data-stu-id="0ca19-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="0ca19-132">**Производственный календарь**</span><span class="sxs-lookup"><span data-stu-id="0ca19-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="0ca19-133">Выберите этот параметр для создания иерархии времени на основе производственного календаря.</span><span class="sxs-lookup"><span data-stu-id="0ca19-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="0ca19-134">**Неделя и месяц начала**</span><span class="sxs-lookup"><span data-stu-id="0ca19-134">**Start week and month**</span></span>  
 <span data-ttu-id="0ca19-135">Выберите неделю и месяц начала производственного календаря.</span><span class="sxs-lookup"><span data-stu-id="0ca19-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-136"> Этот параметр доступен только тогда, когда выбран пункт **Производственный календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-137">**Квартал с дополнительными периодами**</span><span class="sxs-lookup"><span data-stu-id="0ca19-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="0ca19-138">Выберите или введите квартал, содержащий дополнительные периоды.</span><span class="sxs-lookup"><span data-stu-id="0ca19-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca19-139"> Этот параметр доступен только тогда, когда выбран пункт **Производственный календарь** .</span><span class="sxs-lookup"><span data-stu-id="0ca19-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="0ca19-140">**Календарь ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="0ca19-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="0ca19-141">Выберите этот параметр для создания иерархии времени на основе календаря ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="0ca19-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca19-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ca19-142">See Also</span></span>  
 <span data-ttu-id="0ca19-143">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0ca19-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="0ca19-144">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0ca19-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0ca19-145">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="0ca19-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
