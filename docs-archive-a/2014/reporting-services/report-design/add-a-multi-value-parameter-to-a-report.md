---
title: Добавление в отчет параметра с несколькими значениями | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729078"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="91109-102">Добавление в отчет параметра с несколькими значениями</span><span class="sxs-lookup"><span data-stu-id="91109-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="91109-103">В отчет можно добавить параметр, который позволит пользователю выбирать несколько значений для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="91109-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="91109-104">Можно передавать отчету несколько значений параметра в URL-адресе отчета.</span><span class="sxs-lookup"><span data-stu-id="91109-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="91109-105">Пример URL-адреса, содержащего многозначный параметр, см. в разделе [Передача параметров отчета в URL-адресе](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="91109-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="91109-106">Сведения о том, как передавать несколько значений параметра хранимой процедуре, см. в статье [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) (Работа с многозначными параметрами для отчетов служб SSRS) на сайте mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="91109-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="91109-107">Добавление многозначного параметра</span><span class="sxs-lookup"><span data-stu-id="91109-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="91109-108">В построителе отчетов откройте отчет, в который требуется добавить многозначный параметр.</span><span class="sxs-lookup"><span data-stu-id="91109-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="91109-109">Щелкните правой кнопкой мыши набор данных отчета и выберите пункт **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="91109-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="91109-110">Добавьте переменную в запрос к набору данных, либо изменив текст запроса в поле **Запрос** , либо добавив фильтр с помощью конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="91109-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="91109-111">Дополнительные сведения см. в статье [Построение запроса в конструкторе реляционных запросов (построитель отчетов и службы SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91109-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-112">Текст запроса не должен включать инструкцию DECLARE для переменной запроса.</span><span class="sxs-lookup"><span data-stu-id="91109-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-113">Текст для переменной запроса должен содержать оператор `IN`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="91109-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-114">Если не включить круглые скобки вокруг переменной, как показано выше, отчет не будет отображен и отобразится сообщение об ошибке "необходимо объявить скалярную переменную".</span><span class="sxs-lookup"><span data-stu-id="91109-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="91109-115">Параметр набора данных для внедренного или общего набора данных создается для переменной запроса автоматически.</span><span class="sxs-lookup"><span data-stu-id="91109-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="91109-116">Параметр отчета создается автоматически для параметра набора данных.</span><span class="sxs-lookup"><span data-stu-id="91109-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="91109-117">В области **Данные отчета** разверните узел **Параметры** , щелкните правой кнопкой мыши параметр отчета, созданный автоматически для параметра набора данных, а затем щелкните **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="91109-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="91109-118">На вкладке **Общие** выберите **Разрешить несколько значений** , чтобы позволить пользователю выбирать несколько значений для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="91109-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="91109-119">На вкладке значений **Доступные** укажите список значений, которые могут быть отображены для пользователя (необязательно).</span><span class="sxs-lookup"><span data-stu-id="91109-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="91109-120">Список допустимых значений ограничивает значения, которые может выбрать пользователь, набором допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="91109-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="91109-121">В случае нескольких значений в верхней позиции списка будет расположено значение **Выделить все** , предоставляя пользователю возможность выбрать или очистить все значения одним щелчком.</span><span class="sxs-lookup"><span data-stu-id="91109-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="91109-122">Если значения, доступные для параметра отчета, выбираются из запроса к набору данных, следует выбрать набор данных, который не содержит переменной запроса, которая связана с тем же параметром запроса.</span><span class="sxs-lookup"><span data-stu-id="91109-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="91109-123">Дополнительные сведения см. в разделе [Добавление, изменение и удаление допустимых значений параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="91109-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="91109-124">Добавление многозначного параметра</span><span class="sxs-lookup"><span data-stu-id="91109-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="91109-125">В построителе отчетов откройте отчет, в который требуется добавить многозначный параметр.</span><span class="sxs-lookup"><span data-stu-id="91109-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="91109-126">Щелкните правой кнопкой мыши набор данных отчета и выберите пункт **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="91109-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="91109-127">Добавьте переменную в запрос к набору данных, либо изменив текст запроса в поле **Запрос** , либо добавив фильтр с помощью конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="91109-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="91109-128">Дополнительные сведения см. в статье [Построение запроса в конструкторе реляционных запросов (построитель отчетов и службы SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91109-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-129">Текст запроса не должен включать инструкцию DECLARE для переменной запроса.</span><span class="sxs-lookup"><span data-stu-id="91109-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-130">Текст для переменной запроса должен содержать оператор `IN`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="91109-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91109-131">Если не включить круглые скобки вокруг переменной, как показано выше, отчет не будет отображен и отобразится сообщение об ошибке "необходимо объявить скалярную переменную".</span><span class="sxs-lookup"><span data-stu-id="91109-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="91109-132">Параметр набора данных для внедренного или общего набора данных создается для переменной запроса автоматически.</span><span class="sxs-lookup"><span data-stu-id="91109-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="91109-133">Параметр отчета создается автоматически для параметра набора данных.</span><span class="sxs-lookup"><span data-stu-id="91109-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="91109-134">В области **Данные отчета** разверните узел **Параметры** , щелкните правой кнопкой мыши параметр отчета, созданный автоматически для параметра набора данных, а затем щелкните **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="91109-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="91109-135">На вкладке **Общие** выберите **Разрешить несколько значений** , чтобы позволить пользователю выбирать несколько значений для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="91109-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="91109-136">На вкладке значений **Доступные** укажите список значений, которые могут быть отображены для пользователя (необязательно).</span><span class="sxs-lookup"><span data-stu-id="91109-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="91109-137">Список допустимых значений ограничивает значения, которые может выбрать пользователь, набором допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="91109-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="91109-138">В случае нескольких значений в верхней позиции списка будет расположено значение **Выделить все** , предоставляя пользователю возможность выбрать или очистить все значения одним щелчком.</span><span class="sxs-lookup"><span data-stu-id="91109-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="91109-139">Если значения, доступные для параметра отчета, выбираются из запроса к набору данных, следует выбрать набор данных, который не содержит переменной запроса, которая связана с тем же параметром запроса.</span><span class="sxs-lookup"><span data-stu-id="91109-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="91109-140">Дополнительные сведения см. в разделе [Добавление, изменение и удаление допустимых значений параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="91109-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91109-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="91109-141">See Also</span></span>  
 <span data-ttu-id="91109-142">[Добавление каскадных параметров в построитель отчетов &#40;отчетов и SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91109-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="91109-143">Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="91109-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
