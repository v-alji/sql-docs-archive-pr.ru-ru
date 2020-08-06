---
title: Редактор форм ключевых показателей эффективности (вкладка «Ключевые показатели эффективности», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c88d6fcec60634f37ddad8b6d0f5cb2124fa1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656663"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="283f9-102">Редактор формы ключевого показателя эффективности (вкладка «Ключевые показатели эффективности», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="283f9-102">KPI Form Editor (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="283f9-103">Панель **Редактор формы ключевого показателя эффективности** на вкладке **Ключевые показатели эффективности** в конструкторе кубов используется для создания или изменения выбранного ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-103">Use the **KPI Form Editor** pane on the **KPIs** tab in Cube Designer to create or modify the selected Key Performance Indicator (KPI).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-104">Данная панель отображается только в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="283f9-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="283f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="283f9-105">Options</span></span>  
 <span data-ttu-id="283f9-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="283f9-106">**Name**</span></span>  
 <span data-ttu-id="283f9-107">Введите имя ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-107">Type the name of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-108">**Связанная группа мер**</span><span class="sxs-lookup"><span data-stu-id="283f9-108">**Associated measure group**</span></span>  
 <span data-ttu-id="283f9-109">Выберите группу мер, связанную с ключевым показателем эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-109">Select the measure group associated with the KPI.</span></span> <span data-ttu-id="283f9-110">Клиентское приложение может использовать эти сведения, чтобы определить доступные измерения во время просмотра пользователем этого ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-110">The client application can use this information to determine which dimensions are available when the user browses this KPI.</span></span>  
  
 <span data-ttu-id="283f9-111">**Выражение значения**</span><span class="sxs-lookup"><span data-stu-id="283f9-111">**Value Expression**</span></span>  
 <span data-ttu-id="283f9-112">Разверните, чтобы просмотреть или отредактировать многомерные выражения для значения ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-112">Expand to view or edit the Multidimensional Expressions (MDX) expression for the value of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-113">Введите многомерное выражение, которое возвращает значение ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-113">Type the MDX expression that returns the value of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-114">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-114">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="283f9-115">**Целевое выражение**</span><span class="sxs-lookup"><span data-stu-id="283f9-115">**Goal Expression**</span></span>  
 <span data-ttu-id="283f9-116">Разверните, чтобы просмотреть или изменить многомерное выражение для значения цели ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-116">Expand to view or edit the MDX expression for the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-117">Введите многомерное выражение, которое возвращает целевое значение выполняемого ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-117">Type the MDX expression that returns the goal value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="283f9-118">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-118">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="283f9-119">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="283f9-119">**Status**</span></span>  
 <span data-ttu-id="283f9-120">Разверните для просмотра параметров **Изображение состояния** и **Выражение состояния** .</span><span class="sxs-lookup"><span data-stu-id="283f9-120">Expand to view the **Status graphic** and **Status expression** options.</span></span>  
  
 <span data-ttu-id="283f9-121">**Изображение состояния**</span><span class="sxs-lookup"><span data-stu-id="283f9-121">**Status graphic**</span></span>  
 <span data-ttu-id="283f9-122">Выберите изображение, которое будет использоваться клиентским приложением для представления значения состояния в графической форме.</span><span class="sxs-lookup"><span data-stu-id="283f9-122">Select the graphic to be used by the client application to represent the status value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-123">Клиентское приложение может поддерживать выбранное изображение или заменить его на другое подходящее изображение.</span><span class="sxs-lookup"><span data-stu-id="283f9-123">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="283f9-124">**Выражение состояния**</span><span class="sxs-lookup"><span data-stu-id="283f9-124">**Status expression**</span></span>  
 <span data-ttu-id="283f9-125">Введите многомерное выражение, которое возвращает значение состояния выполняемого ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-125">Type the MDX expression that returns the status value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="283f9-126">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-126">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="283f9-127">Рекомендуется, чтобы это выражение возвращало десятичное число в диапазоне от-1 до 1.</span><span class="sxs-lookup"><span data-stu-id="283f9-127">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="283f9-128">Отрицательные числа соответствуют негативной ситуации, положительные — позитивной.</span><span class="sxs-lookup"><span data-stu-id="283f9-128">A lower number represents a negative situation, while a higher number represents a positive situation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-129">Значения ниже-1 и выше 1 возможны, но могут быть неправильно интерпретированы клиентскими приложениями сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="283f9-129">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="283f9-130">**Тренд**</span><span class="sxs-lookup"><span data-stu-id="283f9-130">**Trend**</span></span>  
 <span data-ttu-id="283f9-131">Разверните для просмотра параметров **Изображение тренда** и **Выражение тренда** .</span><span class="sxs-lookup"><span data-stu-id="283f9-131">Expand to view the **Trend graphic** and **Trend expression** options.</span></span>  
  
 <span data-ttu-id="283f9-132">**Изображение тренда**</span><span class="sxs-lookup"><span data-stu-id="283f9-132">**Trend graphic**</span></span>  
 <span data-ttu-id="283f9-133">Выберите изображение, которое будет использоваться клиентским приложением для представления значения тренда в графической форме.</span><span class="sxs-lookup"><span data-stu-id="283f9-133">Select the graphic to be used by the client application to represent the trend value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-134">Клиентское приложение может поддерживать выбранное изображение или заменить его на другое подходящее изображение.</span><span class="sxs-lookup"><span data-stu-id="283f9-134">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="283f9-135">**Выражение тренда**</span><span class="sxs-lookup"><span data-stu-id="283f9-135">**Trend expression**</span></span>  
 <span data-ttu-id="283f9-136">Введите многомерное выражение, которое возвращает значение тренда ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-136">Type the MDX expression that returns the trend value of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-137">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-137">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="283f9-138">Выражение тренда может основываться на любом временном критерии, имеющем смысл в данном контексте бизнеса.</span><span class="sxs-lookup"><span data-stu-id="283f9-138">The trend expression can be based on any time-based criteria that makes sense in a given business context.</span></span> <span data-ttu-id="283f9-139">Рекомендуется, чтобы это выражение возвращало десятичное число в диапазоне от-1 до 1.</span><span class="sxs-lookup"><span data-stu-id="283f9-139">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="283f9-140">Отрицательные числа соответствуют негативному тренду в течение времени, положительные — позитивному тренду.</span><span class="sxs-lookup"><span data-stu-id="283f9-140">A lower number represents a negative trend over time; a higher number represents a positive trend over time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-141">Значения ниже-1 и выше 1 возможны, но могут быть неправильно интерпретированы клиентскими приложениями сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="283f9-141">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="283f9-142">**Дополнительные свойства**</span><span class="sxs-lookup"><span data-stu-id="283f9-142">**Additional Properties**</span></span>  
 <span data-ttu-id="283f9-143">Разверните для просмотра параметров: **Папка отображения**, **Родительский ключевой показатель эффективности**, **Текущий элемент времени**, **Вес**и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="283f9-143">Expand to view the **Display folder**, **Parent KPI**, **Current time member**, **Weight**, and **Description** options.</span></span>  
  
 <span data-ttu-id="283f9-144">**Папка отображения**</span><span class="sxs-lookup"><span data-stu-id="283f9-144">**Display folder**</span></span>  
 <span data-ttu-id="283f9-145">Задайте категоризацию ключевого показателя эффективности, который клиентское приложение использует для отображения.</span><span class="sxs-lookup"><span data-stu-id="283f9-145">Type the categorization of the KPI for use by the client application for display purposes.</span></span>  
  
 <span data-ttu-id="283f9-146">Для разделения имен отдельных папок в папке отображения используйте символ обратной косой черты (\\), для разделения папок отображения используйте точку с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="283f9-146">Use a backward slash (\\) to separate folder names in a display folder and a semicolon (;) to separate multiple display folders.</span></span> <span data-ttu-id="283f9-147">Например, введите `Category\Goal\Scientific;Category\Goal\Metric`.</span><span class="sxs-lookup"><span data-stu-id="283f9-147">For example, type `Category\Goal\Scientific;Category\Goal\Metric`.</span></span>  
  
 <span data-ttu-id="283f9-148">**Родительский ключевой показатель эффективности**</span><span class="sxs-lookup"><span data-stu-id="283f9-148">**Parent KPI**</span></span>  
 <span data-ttu-id="283f9-149">Выберите существующий ключевой показатель эффективности, по которому будут классифицироваться ключевые показатели эффективности для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="283f9-149">Select an existing KPI under which to categorize the KPI for use by the client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283f9-150">Если этот параметр задан в существующем ключевом показателе эффективности, то **Папка отображения** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="283f9-150">If this option is set to an existing KPI, **Display folder** is ignored.</span></span>  
  
 <span data-ttu-id="283f9-151">**Текущий элемент времени**</span><span class="sxs-lookup"><span data-stu-id="283f9-151">**Current time member**</span></span>  
 <span data-ttu-id="283f9-152">Введите многомерное выражение, которое возвращает элемент, идентифицирующий временный контекст ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-152">Type the MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-153">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="283f9-154">Многомерное выражение должно возвращать уникальное имя элемента в пределах измерения времени, связанного с группой мер, определенных для параметра **Связанная группа мер**.</span><span class="sxs-lookup"><span data-stu-id="283f9-154">The MDX expression must return the unique name of a member within a time dimension associated with the measure group specified in **Associated measure group**.</span></span>  
  
 <span data-ttu-id="283f9-155">**Weight**</span><span class="sxs-lookup"><span data-stu-id="283f9-155">**Weight**</span></span>  
 <span data-ttu-id="283f9-156">Разверните, чтобы просмотреть или изменить многомерное выражение для весового коэффициента ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-156">Expand to view or edit the MDX expression for the weighting factor of the KPI.</span></span>  
  
 <span data-ttu-id="283f9-157">Перетащите выбранные элементы с панели **Средства вычисления** в данный параметр, чтобы присоединить синтаксическую структуру многомерного выражения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="283f9-157">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="283f9-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="283f9-158">**Description**</span></span>  
 <span data-ttu-id="283f9-159">Введите описание (необязательно) ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="283f9-159">Type the optional description of the KPI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="283f9-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="283f9-160">See Also</span></span>  
 [<span data-ttu-id="283f9-161">Ключевые показатели эффективности &#40;конструктора кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="283f9-161">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
