---
title: Добавление, изменение или удаление допустимых значений параметра отчета (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportparameters.availablevalues.f1
- "10455"
- "10071"
ms.assetid: 0e03264c-523f-4c59-b71b-ceef600f75f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 985ab3e8dc1d74f94e7242ff57f46ffe4fba9586
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663974"
---
# <a name="add-change-or-delete-available-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="f4aff-102">Добавление, изменение и удаление допустимых значений параметра отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f4aff-102">Add, Change, or Delete Available Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f4aff-103">После создания параметра отчета можно указать список допустимых значений, которые будут выведены для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4aff-103">After you create a report parameter, you can specify a list of available values to display to the user.</span></span> <span data-ttu-id="f4aff-104">Список допустимых значений ограничивает значения, которые может выбрать пользователь, набором допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="f4aff-104">An available values list limits the choices a user can make to only valid values for the parameter.</span></span>  
  
 <span data-ttu-id="f4aff-105">Допустимые значения выводятся в раскрывающемся списке рядом с параметром отчета на панели инструментов при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="f4aff-105">Available values appear in a drop-down list next to the report parameter on the toolbar when the report runs.</span></span> <span data-ttu-id="f4aff-106">Параметры отчета могут представлять одно или несколько значений.</span><span class="sxs-lookup"><span data-stu-id="f4aff-106">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="f4aff-107">В случае нескольких значений в верхней позиции списка будет расположено значение **Выделить все** , предоставляя пользователю возможность выбрать или очистить все значения одним щелчком.</span><span class="sxs-lookup"><span data-stu-id="f4aff-107">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span>  
  
 <span data-ttu-id="f4aff-108">Можно предоставить статический список значений или список из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="f4aff-108">You can provide a static list of values or a list from a report dataset.</span></span> <span data-ttu-id="f4aff-109">Дополнительно значениям можно присвоить понятные имена, указав значение в поле метки.</span><span class="sxs-lookup"><span data-stu-id="f4aff-109">You can optionally provide a friendly name for values by specifying a label field.</span></span> <span data-ttu-id="f4aff-110">Например, для параметра на основе поля `ProductID` можно вывести в метке параметра поле `ProductName` .</span><span class="sxs-lookup"><span data-stu-id="f4aff-110">For example, for a parameter based on a `ProductID` field, you can display the `ProductName` field in the parameter label.</span></span> <span data-ttu-id="f4aff-111">При работе отчета пользователь сможет выбирать названия продуктов, но на самом деле выбранное значение будет соответствовать полю `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="f4aff-111">When the report runs, the user can choose from the product names, but the actual chosen value is the corresponding `ProductID`.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="f4aff-112">После публикации отчета можно изменить доступные значения, определяемые в отчете с помощью средства разработки отчетов, задавая значения свойств параметров на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="f4aff-112">After you publish a report, you can override the available values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="f4aff-113">Дополнительные сведения см. в разделе [Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f4aff-113">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
### <a name="to-add-or-change-the-available-values-for-a-report-parameter"></a><span data-ttu-id="f4aff-114">Добавление или изменение допустимых значений параметра отчета</span><span class="sxs-lookup"><span data-stu-id="f4aff-114">To add or change the available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="f4aff-115">В области данных отчета разверните узел «Параметры».</span><span class="sxs-lookup"><span data-stu-id="f4aff-115">In the Report Data pane, expand the Parameters node.</span></span> <span data-ttu-id="f4aff-116">Щелкните правой кнопкой мыши параметр и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-116">Right-click the parameter and click **Parameter Properties**.</span></span> <span data-ttu-id="f4aff-117">Откроется диалоговое окно **Свойства параметра отчета** .</span><span class="sxs-lookup"><span data-stu-id="f4aff-117">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4aff-118">Если область данных отчета не появилась, в меню **Вид** выберите команду **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-118">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="f4aff-119">Нажмите кнопку **Допустимые значения**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-119">Click **Available Values**.</span></span> <span data-ttu-id="f4aff-120">Выберите параметр допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="f4aff-120">Select an available values option:</span></span>  
  
    -   <span data-ttu-id="f4aff-121">Нажмите кнопку **Указать значения** , чтобы вручную ввести список значений, и, по желанию, понятные имена (метки) для значений.</span><span class="sxs-lookup"><span data-stu-id="f4aff-121">Click **Specify values** to manually provide a list of values, and optionally, friendly names (the labels) for the values.</span></span>  
  
         <span data-ttu-id="f4aff-122">Нажмите кнопку **Добавить** и введите значение в текстовое поле **Значение** и, по желанию, метку в текстовое поле **Метка** .</span><span class="sxs-lookup"><span data-stu-id="f4aff-122">Click **Add** and then enter the value in the **Value** text box, and optionally, the label in the **Label** text box.</span></span> <span data-ttu-id="f4aff-123">Если не указать метку, будет использовано значение.</span><span class="sxs-lookup"><span data-stu-id="f4aff-123">If you do not provide a label, the value is used.</span></span> <span data-ttu-id="f4aff-124">Для значения можно записать выражение.</span><span class="sxs-lookup"><span data-stu-id="f4aff-124">You can write an expression for a value.</span></span> <span data-ttu-id="f4aff-125">Тип данных должен соответствовать типу данных параметра.</span><span class="sxs-lookup"><span data-stu-id="f4aff-125">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="f4aff-126">Нельзя задавать параметры в выражении с помощью имен полей.</span><span class="sxs-lookup"><span data-stu-id="f4aff-126">Field names cannot be used in an expression for a parameter.</span></span> <span data-ttu-id="f4aff-127">Примеры см. в разделе [Часто используемые фильтры (построитель отчетов и службы SSRS)](commonly-used-filters-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4aff-127">For examples, see [Commonly Used Filters &#40;Report Builder and SSRS&#41;](commonly-used-filters-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="f4aff-128">Повторите этот шаг для всех значений, которые нужно указать.</span><span class="sxs-lookup"><span data-stu-id="f4aff-128">Repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="f4aff-129">Порядок, в котором значения отображаются в данном списке, определяет порядок, в котором пользователь увидит их в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="f4aff-129">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="f4aff-130">Чтобы изменить порядок элементов списка, щелкните текстовое поле **Значение** или **Метка** , чтобы выбрать элемент, а потом с помощью кнопок со стрелками вверх и вниз переместите выбранный элемент вверх или вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="f4aff-130">To change the order of an item in the list, click a **Value** or **Label** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="f4aff-131">Чтобы ввести имя существующего набора данных, который получает значения и, по желанию, понятные имена для данного параметра, щелкните **Получать значения из запроса** .</span><span class="sxs-lookup"><span data-stu-id="f4aff-131">Click **Get values from a query** to provide the name of an existing dataset that retrieves the values, and optionally, the friendly names for this parameter.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="f4aff-132">Если один и тот же набор данных содержит параметр запроса, соответствующий параметру отчета, то отчет отобразит сообщение об ошибке при попытке запустить его.</span><span class="sxs-lookup"><span data-stu-id="f4aff-132">If the same dataset contains the corresponding query parameter for the report parameter, the report will display an error message when you try to run it.</span></span> <span data-ttu-id="f4aff-133">Эту ошибку можно устранить, использовав другой набор данных для получения значений.</span><span class="sxs-lookup"><span data-stu-id="f4aff-133">You resolve this error by using a different dataset to retrieve the values.</span></span>  
  
         <span data-ttu-id="f4aff-134">В поле **Набор данных**введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="f4aff-134">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="f4aff-135">В поле **Поле значения**выберите имя поля, которое предоставляет значения параметра.</span><span class="sxs-lookup"><span data-stu-id="f4aff-135">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
         <span data-ttu-id="f4aff-136">В поле **Поле метки**выберите имя поля, предоставляющего понятные имена для параметра.</span><span class="sxs-lookup"><span data-stu-id="f4aff-136">In **Label field**, choose the name of the field that provides the friendly names for the parameter.</span></span> <span data-ttu-id="f4aff-137">Если для понятных имен нет отдельного поля, выберите поле, которое было выбрано для поля **Значение** .</span><span class="sxs-lookup"><span data-stu-id="f4aff-137">If there is no separate field for friendly names, choose the same field as you chose for the **Value** field.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="f4aff-138">При предварительном просмотре отчета можно увидеть раскрывающийся список допустимых значений параметра.</span><span class="sxs-lookup"><span data-stu-id="f4aff-138">When you preview the report, you see a drop-down list of available values for the parameter.</span></span>  
  
### <a name="to-remove-the-available-values-for-a-report-parameter"></a><span data-ttu-id="f4aff-139">Удаление допустимых значений параметра отчета</span><span class="sxs-lookup"><span data-stu-id="f4aff-139">To remove the available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="f4aff-140">В области данных отчета разверните узел «Параметры».</span><span class="sxs-lookup"><span data-stu-id="f4aff-140">In the Report Data pane, expand the Parameters node.</span></span> <span data-ttu-id="f4aff-141">Щелкните правой кнопкой мыши параметр и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-141">Right-click the parameter and click **Parameter Properties**.</span></span> <span data-ttu-id="f4aff-142">Откроется диалоговое окно **Параметры отчета** .</span><span class="sxs-lookup"><span data-stu-id="f4aff-142">The **Report Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f4aff-143">Нажмите кнопку **Допустимые значения**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-143">Click **Available Values**.</span></span>  
  
3.  <span data-ttu-id="f4aff-144">В поле **Выберите один из следующих параметров**укажите значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="f4aff-144">In **Select from one of the following options**, click **None**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="f4aff-145">При предварительном просмотре отчета можно увидеть, что для данного параметра раскрывающийся список допустимых значений больше не появляется.</span><span class="sxs-lookup"><span data-stu-id="f4aff-145">When you preview the report, you the drop-down list of available values for the parameter no longer appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4aff-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4aff-146">See Also</span></span>  
 <span data-ttu-id="f4aff-147">[Изменение порядка параметров отчета (построитель отчетов и службы SSRS)](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-147">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4aff-148">[Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-148">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4aff-149">[Добавление каскадных параметров в отчет (построитель отчетов и службы SSRS)](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-149">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4aff-150">[Добавление, изменение или удаление значения по умолчанию для параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-150">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="f4aff-151">[Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-151">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="f4aff-152">[Учебник. Добавление параметра к отчету (построитель отчетов)](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="f4aff-152">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="f4aff-153">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f4aff-153">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
