---
title: Добавление, изменение и обновление полей в области данных отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654850"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="925ea-102">Добавление, изменение и обновление полей в области данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="925ea-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="925ea-103">Поля набора данных являются встроенной коллекцией имен полей, представляющей данные, возвращаемые при выполнении запроса к внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="925ea-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="925ea-104">Для внедренного набора данных полями набора данных являются поля, созданные после завершения построения запроса и закрытия панели «Конструктор запросов», а также создаваемые вычисляемые поля.</span><span class="sxs-lookup"><span data-stu-id="925ea-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="925ea-105">Для общего набора данных полями набора данных являются поля определения общего набора данных при его добавлении к отчету.</span><span class="sxs-lookup"><span data-stu-id="925ea-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="925ea-106">Хотя запрос из общего набора данных на сервере отчетов всегда используется при выполнении отчета, список полей наборов данных в отчете является статичным.</span><span class="sxs-lookup"><span data-stu-id="925ea-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="925ea-107">Чтобы обновить список полей в отчете для соответствия текущему списку полей в запросе общего набора данных используйте кнопку **Обновить поля** .</span><span class="sxs-lookup"><span data-stu-id="925ea-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="925ea-108">Обновление полей не влияет на вычисляемые поля, определенные в отчете.</span><span class="sxs-lookup"><span data-stu-id="925ea-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="925ea-109">Добавление поля запроса</span><span class="sxs-lookup"><span data-stu-id="925ea-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="925ea-110">В области данных отчета щелкните правой кнопкой мыши набор данных и выберите команду **Добавить поле запроса**.</span><span class="sxs-lookup"><span data-stu-id="925ea-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="925ea-111">Если область данных отчета не видна, в меню **Вид** выберите пункт **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="925ea-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="925ea-112">На странице **Поля** диалогового окна **Свойства набора данных** нажмите кнопку **Добавить**, затем выберите **Поле запроса**.</span><span class="sxs-lookup"><span data-stu-id="925ea-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="925ea-113">Новая строка добавляется в сетку снизу.</span><span class="sxs-lookup"><span data-stu-id="925ea-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="925ea-114">В текстовое поле **Имя поля** введите имя поля.</span><span class="sxs-lookup"><span data-stu-id="925ea-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="925ea-115">В пределах набора данных имена должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="925ea-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="925ea-116">В текстовое поле **Источник поля** введите имя существующего поля источника данных.</span><span class="sxs-lookup"><span data-stu-id="925ea-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="925ea-117">Добавление вычисляемого поля</span><span class="sxs-lookup"><span data-stu-id="925ea-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="925ea-118">В области данных отчета щелкните правой кнопкой мыши набор данных и выберите команду **Добавить вычисляемое поле**.</span><span class="sxs-lookup"><span data-stu-id="925ea-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="925ea-119">На странице **Поля** диалогового окна **Свойства набора данных** нажмите кнопку **Добавить**и выберите **Вычисляемое поле**.</span><span class="sxs-lookup"><span data-stu-id="925ea-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="925ea-120">Новая строка добавляется в сетку снизу.</span><span class="sxs-lookup"><span data-stu-id="925ea-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="925ea-121">В текстовое поле **Имя поля** введите имя поля.</span><span class="sxs-lookup"><span data-stu-id="925ea-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="925ea-122">В пределах набора данных имена должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="925ea-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="925ea-123">В текстовое поле **Источник поля** введите выражение для поля.</span><span class="sxs-lookup"><span data-stu-id="925ea-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="925ea-124">Нажмите кнопку выражения (**fx**), чтобы создать выражение.</span><span class="sxs-lookup"><span data-stu-id="925ea-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="925ea-125">Выражение для вычисляемого поля не может содержать статистических выражений или ссылок на элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="925ea-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="925ea-126">Изменение поля запроса или поля набора данных</span><span class="sxs-lookup"><span data-stu-id="925ea-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="925ea-127">В области данных отчета щелкните правой кнопкой мыши поле и выберите пункт **Свойства поля**.</span><span class="sxs-lookup"><span data-stu-id="925ea-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="925ea-128">На странице **Поля** диалогового окна **Свойства набора данных** щелкните существующее поле, чтобы выбрать строку.</span><span class="sxs-lookup"><span data-stu-id="925ea-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="925ea-129">Измените имя или значение поля.</span><span class="sxs-lookup"><span data-stu-id="925ea-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="925ea-130">Удаление поля запроса или вычисляемого поля</span><span class="sxs-lookup"><span data-stu-id="925ea-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="925ea-131">В области данных отчета разверните набор данных, чтобы отобразить коллекцию полей.</span><span class="sxs-lookup"><span data-stu-id="925ea-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="925ea-132">Щелкните правой кнопкой мыши поле, которое хотите удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="925ea-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="925ea-133">Обновление коллекции полей в области данных отчета для общего набора данных</span><span class="sxs-lookup"><span data-stu-id="925ea-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="925ea-134">В области данных отчета щелкните правой кнопкой мыши набор данных и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="925ea-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="925ea-135">Нажмите кнопку **Обновить поля**.</span><span class="sxs-lookup"><span data-stu-id="925ea-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="925ea-136">На сервере отчетов выполняется запрос общего набора данных, который возвращает коллекцию текущих полей.</span><span class="sxs-lookup"><span data-stu-id="925ea-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925ea-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="925ea-137">See Also</span></span>  
 <span data-ttu-id="925ea-138">[Коллекция полей набора данных (построитель отчетов и службы SSRS)](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="925ea-139">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="925ea-140">[Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="925ea-141">[Конструкторы запросов служб Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="925ea-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="925ea-142">Конструкторы запросов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="925ea-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
