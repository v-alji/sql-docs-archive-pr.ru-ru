---
title: Добавление, изменение или удаление значений по умолчанию для параметра отчета (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663980"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="33651-102">Добавление, изменение или удаление значения по умолчанию для параметра отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="33651-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="33651-103">После создания параметров отчета можно предоставить список значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33651-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="33651-104">Если все параметры имеют допустимые значения по умолчанию, отчет запускается автоматически при первом просмотре.</span><span class="sxs-lookup"><span data-stu-id="33651-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="33651-105">Параметры отчета могут представлять одно или несколько значений.</span><span class="sxs-lookup"><span data-stu-id="33651-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="33651-106">В качестве одного значения можно указать литерал или выражение.</span><span class="sxs-lookup"><span data-stu-id="33651-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="33651-107">При указании нескольких значений можно предоставить статический список или список из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="33651-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="33651-108">После публикации отчета можно изменить значения по умолчанию, определяемые в отчете с помощью средства разработки отчетов, задавая значения свойств параметров на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="33651-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="33651-109">Для параметра можно также предоставить несколько наборов значений по умолчанию, создав связанные отчеты.</span><span class="sxs-lookup"><span data-stu-id="33651-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="33651-110">Дополнительные сведения см. в разделе  [Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="33651-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="33651-111">Добавление или изменение значений по умолчанию для параметра отчета</span><span class="sxs-lookup"><span data-stu-id="33651-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="33651-112">В области данных отчета разверните узел **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="33651-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="33651-113">Щелкните правой кнопкой мыши параметр и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33651-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="33651-114">Откроется диалоговое окно **Свойства параметра отчета** .</span><span class="sxs-lookup"><span data-stu-id="33651-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33651-115">Если область данных отчета не появилась, в меню **Вид** выберите команду **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="33651-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="33651-116">Нажмите кнопку **Значения по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="33651-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="33651-117">Выберите параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33651-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="33651-118">Чтобы вручную указать значение или список значений, нажмите кнопку **Указать значения**.</span><span class="sxs-lookup"><span data-stu-id="33651-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="33651-119">Нажмите кнопку **Добавить** и введите значение в текстовое поле **Значение** .</span><span class="sxs-lookup"><span data-stu-id="33651-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="33651-120">Для значения можно записать выражение.</span><span class="sxs-lookup"><span data-stu-id="33651-120">You can write an expression for a value.</span></span> <span data-ttu-id="33651-121">Тип данных должен соответствовать типу данных параметра.</span><span class="sxs-lookup"><span data-stu-id="33651-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="33651-122">Нельзя задавать параметры в выражении с помощью имен полей.</span><span class="sxs-lookup"><span data-stu-id="33651-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="33651-123">Для многозначных параметров повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="33651-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="33651-124">Порядок, в котором значения отображаются в данном списке, определяет порядок, в котором пользователь увидит их в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="33651-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="33651-125">Чтобы изменить порядок элементов списка, щелкните текстовое поле **Значение** , чтобы выбрать элемент, а потом с помощью кнопок со стрелками вверх и вниз переместите выбранный элемент вверх или вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="33651-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="33651-126">Чтобы предоставить имя существующего набора данных, получающего значения, щелкните **Получать значения из запроса**.</span><span class="sxs-lookup"><span data-stu-id="33651-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="33651-127">В поле **Набор данных**введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="33651-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="33651-128">В поле **Поле значения**выберите имя поля, которое предоставляет значения параметра.</span><span class="sxs-lookup"><span data-stu-id="33651-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="33651-129">Удаление значений по умолчанию для параметра отчета</span><span class="sxs-lookup"><span data-stu-id="33651-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="33651-130">В области данных отчета разверните узел **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="33651-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="33651-131">Щелкните правой кнопкой мыши параметр и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="33651-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="33651-132">Откроется диалоговое окно **Свойства параметра отчета** .</span><span class="sxs-lookup"><span data-stu-id="33651-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="33651-133">Нажмите кнопку **Значения по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="33651-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="33651-134">В области **Выберите один из следующих параметров**выберите **Нет значения по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="33651-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33651-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="33651-135">See Also</span></span>  
 <span data-ttu-id="33651-136">[Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="33651-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="33651-137">[Добавление каскадных параметров в отчет (построитель отчетов и службы SSRS)](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33651-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="33651-138">[Учебник. Добавление параметра к отчету (построитель отчетов)](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="33651-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="33651-139">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="33651-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="33651-140">[Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="33651-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="33651-141">[Изменение порядка параметров отчета (построитель отчетов и службы SSRS)](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33651-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="33651-142">[Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33651-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="33651-143">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="33651-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
