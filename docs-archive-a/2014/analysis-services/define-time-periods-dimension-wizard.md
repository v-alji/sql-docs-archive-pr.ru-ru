---
title: Определение временных периодов (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667948"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="bb0c7-102">Определение временных периодов (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="bb0c7-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="bb0c7-103">Используйте страницу **Определение временных периодов** , чтобы указать календарные данные для включения в измерение времени или серверное измерение времени.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb0c7-104"> Эта страница появляется только в случае выбора пункта **Серверное измерение времени** на странице **Выбор типа измерения** , либо если было выбран пункт **Построить измерение без использования источника данных** на странице **Выбор метода построения** и **Измерение времени** на странице **Выбор типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="bb0c7-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bb0c7-105">Эта страница предназначена для определения календарного года в измерении времени.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="bb0c7-106">Чтобы определить финансовый, производственный, отчетный год или год по стандарту 8601 Международной организации стандартов (ISO) для измерения времени, используйте страницу **Выбор календарей** .</span><span class="sxs-lookup"><span data-stu-id="bb0c7-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb0c7-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="bb0c7-107">Options</span></span>  
 <span data-ttu-id="bb0c7-108">**Первый день календаря**</span><span class="sxs-lookup"><span data-stu-id="bb0c7-108">**First calendar day**</span></span>  
 <span data-ttu-id="bb0c7-109">Ввести или выбрать день начала текущего года.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="bb0c7-110">**Последний день календаря**</span><span class="sxs-lookup"><span data-stu-id="bb0c7-110">**Last calendar day**</span></span>  
 <span data-ttu-id="bb0c7-111">Ввести или выбрать день окончания текущего года.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="bb0c7-112">**Первый день недели**</span><span class="sxs-lookup"><span data-stu-id="bb0c7-112">**First day of the week**</span></span>  
 <span data-ttu-id="bb0c7-113">Выбрать день начала недели.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="bb0c7-114">**Временные периоды**</span><span class="sxs-lookup"><span data-stu-id="bb0c7-114">**Time periods**</span></span>  
 <span data-ttu-id="bb0c7-115">Выбрать временные периоды для календарного года измерения времени.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb0c7-116">Необходимо указать временной период `Date`.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="bb0c7-117">**Язык отображения имен элементов времени**</span><span class="sxs-lookup"><span data-stu-id="bb0c7-117">**Language for time member names**</span></span>  
 <span data-ttu-id="bb0c7-118">Выбрать язык отображения имен элементов времени.</span><span class="sxs-lookup"><span data-stu-id="bb0c7-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0c7-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb0c7-119">See Also</span></span>  
 <span data-ttu-id="bb0c7-120">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bb0c7-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="bb0c7-121">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb0c7-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="bb0c7-122">[Измерения в многомерных моделях](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="bb0c7-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="bb0c7-123">Мастер выбора календарей &#40;измерения&#41;</span><span class="sxs-lookup"><span data-stu-id="bb0c7-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
