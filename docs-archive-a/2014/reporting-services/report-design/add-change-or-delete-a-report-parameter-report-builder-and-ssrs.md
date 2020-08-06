---
title: Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663986"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="4535d-102">Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4535d-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4535d-103">Параметры отчета позволяют выбирать данные отчета, соединять связанные отчеты и изменять представление отчета.</span><span class="sxs-lookup"><span data-stu-id="4535d-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="4535d-104">Можно предоставить значения по умолчанию и список доступных значений, чтобы пользователи могли их изменять.</span><span class="sxs-lookup"><span data-stu-id="4535d-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="4535d-105">После публикации отчета на сервере отчетов можно изменить значения по умолчанию, доступные значения и другие свойства параметров отчета.</span><span class="sxs-lookup"><span data-stu-id="4535d-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="4535d-106">Для параметра можно предоставить несколько наборов значений по умолчанию, создав связанные отчеты.</span><span class="sxs-lookup"><span data-stu-id="4535d-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="4535d-107">Дополнительные сведения см. в разделе «Установка параметров для опубликованного отчета» в документации по службам [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в [электронной документации по SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="4535d-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="4535d-108">Добавление или изменение параметра отчета</span><span class="sxs-lookup"><span data-stu-id="4535d-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="4535d-109">В области **Данные отчета** щелкните правой кнопкой мыши узел **Параметры** и выберите **Добавить параметр**.</span><span class="sxs-lookup"><span data-stu-id="4535d-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="4535d-110">Откроется диалоговое окно **Свойства параметра отчета** .</span><span class="sxs-lookup"><span data-stu-id="4535d-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="4535d-111">В поле **Имя**введите имя параметра или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4535d-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="4535d-112">В поле **Запрос**введите текст, отображаемый рядом с текстовым полем параметра при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="4535d-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="4535d-113">В поле **Тип данных**выберите тип данных для значения параметра.</span><span class="sxs-lookup"><span data-stu-id="4535d-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="4535d-114">Если параметр может содержать пустое значение, выберите **Разрешить пустое значение**.</span><span class="sxs-lookup"><span data-stu-id="4535d-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="4535d-115">Если параметр может содержать значение NULL, выберите **Разрешить значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="4535d-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="4535d-116">Чтобы разрешить пользователю выбирать несколько значений параметра, выберите **Разрешить несколько значений**.</span><span class="sxs-lookup"><span data-stu-id="4535d-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="4535d-117">Укажите параметр видимости.</span><span class="sxs-lookup"><span data-stu-id="4535d-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="4535d-118">Чтобы отобразить параметр на панели инструментов в верхней части отчета, выберите **Видимый**.</span><span class="sxs-lookup"><span data-stu-id="4535d-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="4535d-119">Чтобы скрыть параметр и не отображать его на панели инструментов, выберите **Скрытый**.</span><span class="sxs-lookup"><span data-stu-id="4535d-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="4535d-120">Чтобы скрыть параметр и защитить его от изменений на сервере отчетов после публикации, выберите **Внутренний**.</span><span class="sxs-lookup"><span data-stu-id="4535d-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="4535d-121">Этот параметр отчета можно будет просмотреть только в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="4535d-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="4535d-122">Для этого параметра необходимо указать значение по умолчанию или разрешить ему принимать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4535d-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="4535d-123">Удаление параметра отчета</span><span class="sxs-lookup"><span data-stu-id="4535d-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="4535d-124">В области **Данные отчета** разверните узел **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="4535d-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="4535d-125">Щелкните правой кнопкой мыши параметр отчета и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4535d-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4535d-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4535d-126">See Also</span></span>  
 <span data-ttu-id="4535d-127">[Добавить, изменить или удалить допустимые значения параметра отчета &#40;построитель отчетов и SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="4535d-128">[Добавление, изменение или удаление значений по умолчанию для параметра отчета &#40;построитель отчетов и служб SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="4535d-129">[Изменение порядка параметров отчета &#40;построитель отчетов и SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4535d-130">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="4535d-131">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="4535d-132">[Добавление каскадных параметров в построитель отчетов &#40;отчетов и SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4535d-133">[Учебник. Добавление параметра в отчет &#40;построитель отчетов&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="4535d-134">[Учебники &#40;построитель отчетов&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="4535d-135">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров &#40;построитель отчетов и SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="4535d-136">[Коллекция Parameters ссылается на &#40;построитель отчетов и SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4535d-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="4535d-137">Добавление в отчет параметра с несколькими значениями</span><span class="sxs-lookup"><span data-stu-id="4535d-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
