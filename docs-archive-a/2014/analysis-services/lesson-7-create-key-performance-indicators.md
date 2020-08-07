---
title: Занятие 8. Создание ключевых показателей эффективности | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731029"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="05b77-102">Урок 8. Создание ключевых показателей эффективности</span><span class="sxs-lookup"><span data-stu-id="05b77-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="05b77-103">На этом занятии мы создадим ключевые показатели эффективности (KPI).</span><span class="sxs-lookup"><span data-stu-id="05b77-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="05b77-104">KPI используются для измерения производительности значения, определенного *базовой* мерой относительно *целевого* значения, определенного мерой, или абсолютного значения.</span><span class="sxs-lookup"><span data-stu-id="05b77-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="05b77-105">В клиентских приложениях по ведению отчетности ключевые показатели эффективности позволяют специалистам быстро и просто получить сводку по успешности бизнеса или выявить тенденции.</span><span class="sxs-lookup"><span data-stu-id="05b77-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="05b77-106">Дополнительные сведения см. в разделе [Ключевые показатели эффективности (табличные службы SSAS)](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="05b77-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="05b77-107">Предполагаемое время выполнения этого занятия: **15 минут**</span><span class="sxs-lookup"><span data-stu-id="05b77-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05b77-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="05b77-108">Prerequisites</span></span>  
 <span data-ttu-id="05b77-109">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="05b77-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="05b77-110">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее занятие: [Занятие 7. Создание мер](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="05b77-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="05b77-111">Создание ключевых показателей эффективности</span><span class="sxs-lookup"><span data-stu-id="05b77-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="05b77-112">Создание ключевых показателей эффективности для интернет-продаж в текущем квартале</span><span class="sxs-lookup"><span data-stu-id="05b77-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="05b77-113">В конструкторе моделей щелкните таблицу (вкладку) **Интернет-продажи** .</span><span class="sxs-lookup"><span data-stu-id="05b77-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="05b77-114">В сетке мер щелкните пустую ячейку.</span><span class="sxs-lookup"><span data-stu-id="05b77-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="05b77-115">В строке формул над таблицей введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="05b77-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="05b77-116">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="05b77-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="05b77-117">Эта мера будет служить базовой мерой для KPI.</span><span class="sxs-lookup"><span data-stu-id="05b77-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="05b77-118">В сетке мер щелкните правой кнопкой мыши меру **Производительность интернет-продаж в текущем квартале** и выберите команду **Создать ключевой показатель эффективности**.</span><span class="sxs-lookup"><span data-stu-id="05b77-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="05b77-119">Откроется диалоговое окно **Ключевой показатель эффективности** .</span><span class="sxs-lookup"><span data-stu-id="05b77-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="05b77-120">В диалоговом окне **Ключевой показатель эффективности** в поле **Определение целевого значения**выберите пункт **Абсолютное значение** .</span><span class="sxs-lookup"><span data-stu-id="05b77-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="05b77-121">В поле **абсолютное значение** введите `1.1` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="05b77-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="05b77-122">В окне **Определение порогов состояния**в левом (нижнем) поле ползунка введите `1` , а затем в правом (высоком) поле ползунка введите `1.07` .</span><span class="sxs-lookup"><span data-stu-id="05b77-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="05b77-123">На вкладке **Выберите стиль значка**выберите тип значков: ромб (красный), треугольник (желтый), круг (зеленый).</span><span class="sxs-lookup"><span data-stu-id="05b77-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="05b77-124">Обратите внимание на раскрываемое поле **Описания** под доступными стилями значков.</span><span class="sxs-lookup"><span data-stu-id="05b77-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="05b77-125">Можно ввести описания для различных элементов KPI, чтобы их было проще найти в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="05b77-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="05b77-126">Чтобы завершить создание ключевого показателя эффективности, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="05b77-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="05b77-127">В сетке мер обратите внимание на значок рядом с мерой **Эффективность интернет-продаж в текущем квартале** .</span><span class="sxs-lookup"><span data-stu-id="05b77-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="05b77-128">Этот значок указывает, что мера служит базовым значением для KPI.</span><span class="sxs-lookup"><span data-stu-id="05b77-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="05b77-129">Создание KPI для измерения эффективности маржи интернет-продаж в текущем квартале</span><span class="sxs-lookup"><span data-stu-id="05b77-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="05b77-130">В сетке мер щелкните пустую ячейку в таблице **Интернет-продажи** .</span><span class="sxs-lookup"><span data-stu-id="05b77-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="05b77-131">В строке формул над таблицей введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="05b77-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="05b77-132">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="05b77-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="05b77-133">В сетке мер щелкните правой кнопкой мыши меру **Производительность маржи интернет-продаж в текущем квартале** и выберите команду **Создать ключевой показатель эффективности**.</span><span class="sxs-lookup"><span data-stu-id="05b77-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="05b77-134">В диалоговом окне **Ключевой показатель эффективности** в поле **Определение целевого значения**выберите пункт **Абсолютное значение** .</span><span class="sxs-lookup"><span data-stu-id="05b77-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="05b77-135">В поле **абсолютное значение** введите `1.25` .</span><span class="sxs-lookup"><span data-stu-id="05b77-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="05b77-136">В поле **Определите пороговые значения состояния**переместите левое (нижнее) поле ползунка так, чтобы в нем отображалось значение **0,8**, а затем переместите правое (верхнее) поле ползунка так, чтобы в нем отображалось значение **1,03**.</span><span class="sxs-lookup"><span data-stu-id="05b77-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="05b77-137">В области **Выберите стиль значка** выберите значок в виде ромба (красного цвета), треугольника (желтого цвета), круга (зеленого цвета) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="05b77-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="05b77-138">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="05b77-138">Next Step</span></span>  
 <span data-ttu-id="05b77-139">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию: [Занятие 9. Создание перспектив](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="05b77-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
