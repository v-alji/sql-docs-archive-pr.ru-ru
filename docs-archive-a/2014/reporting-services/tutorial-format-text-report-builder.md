---
title: Учебник. Форматирование текста (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737805"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="f273c-102">Учебник. Форматирование текста (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="f273c-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="f273c-103">В этом учебнике приведено описание различных способов форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="f273c-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="f273c-104">После настройки пустого отчета с источником данных и набором данных выберите разделы, которые необходимо изучить.</span><span class="sxs-lookup"><span data-stu-id="f273c-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="f273c-105">На приведенном далее рисунке показан отчет, похожий на тот, который будет в итоге создан.</span><span class="sxs-lookup"><span data-stu-id="f273c-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="f273c-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="f273c-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="f273c-107">На одном из этапов будет намеренно допущена ошибка с целью проиллюстрировать, почему именно она является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f273c-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="f273c-108">После этого ошибка будет исправлена для достижения желаемого эффекта.</span><span class="sxs-lookup"><span data-stu-id="f273c-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="f273c-109">Улучшенная версия отчета, созданного в этом учебнике, доступна в качестве образца отчета в построителе отчетов [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f273c-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="f273c-110">Дополнительные сведения о загрузке этого и других образцов отчетов см. в разделе [Образцы отчетов построителя отчетов](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="f273c-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="f273c-111">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="f273c-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="f273c-112">Настройка отчета</span><span class="sxs-lookup"><span data-stu-id="f273c-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="f273c-113">Создание пустого отчета с источником данных и набором данных</span><span class="sxs-lookup"><span data-stu-id="f273c-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="f273c-114">Добавление поля в область конструктора отчетов (неправильным способом, затем правильным способом)</span><span class="sxs-lookup"><span data-stu-id="f273c-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="f273c-115">Добавление таблицы в отчет область конструктора</span><span class="sxs-lookup"><span data-stu-id="f273c-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="f273c-116">Выбор разделов</span><span class="sxs-lookup"><span data-stu-id="f273c-116">Pick and Choose</span></span>  
 [<span data-ttu-id="f273c-117">Добавление гиперссылки в отчет</span><span class="sxs-lookup"><span data-stu-id="f273c-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="f273c-118">Поворот текста в отчете</span><span class="sxs-lookup"><span data-stu-id="f273c-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="f273c-119">Отображение текста с форматированием HTML</span><span class="sxs-lookup"><span data-stu-id="f273c-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="f273c-120">Формат валюты</span><span class="sxs-lookup"><span data-stu-id="f273c-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="f273c-121">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="f273c-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="f273c-122">Предполагаемое время для выполнения заданий данного учебника: 20 минут</span><span class="sxs-lookup"><span data-stu-id="f273c-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f273c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f273c-123">Requirements</span></span>  
 <span data-ttu-id="f273c-124">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="f273c-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="f273c-125">Создание пустого отчета с источником данных и набором данных</span><span class="sxs-lookup"><span data-stu-id="f273c-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="f273c-126">Создание пустого отчета</span><span class="sxs-lookup"><span data-stu-id="f273c-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="f273c-127">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**, а затем щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="f273c-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f273c-128">Должно открыться диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="f273c-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="f273c-129">Если этого не произойдет, из меню для кнопки «Построитель отчетов» выберите команду **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f273c-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="f273c-130">На левой панели диалогового окна **Приступая к работе** проверьте, выбран ли пункт **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="f273c-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="f273c-131">На правой панели щелкните **Пустой отчет**.</span><span class="sxs-lookup"><span data-stu-id="f273c-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="f273c-132">Создание источника данных</span><span class="sxs-lookup"><span data-stu-id="f273c-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="f273c-133">В области данных отчета нажмите кнопку **создать**, а затем выберите **источник данных**.</span><span class="sxs-lookup"><span data-stu-id="f273c-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="f273c-134">В поле **Имя** введите **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="f273c-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="f273c-135">Нажмите кнопку **Использовать соединение, внедренное в отчет**.</span><span class="sxs-lookup"><span data-stu-id="f273c-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="f273c-136">Убедитесь, что тип соединения — Microsoft SQL Server, а затем в поле **строка подключения** введите: \*\*Data Source = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="f273c-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f273c-137">Выражение \<servername>, например Report001, указывает компьютер, на котором установлен экземпляр компонента SQL Server Database Engine.</span><span class="sxs-lookup"><span data-stu-id="f273c-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="f273c-138">Для этого учебника не требуется специальных данных. Необходимо только соединение с базой данных [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f273c-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="f273c-139">Если соединение с источником данных в списке **Соединения с источниками данных**уже есть, выберите его и переходите к следующему этапу, "Создание набора данных".</span><span class="sxs-lookup"><span data-stu-id="f273c-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="f273c-140">Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f273c-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="f273c-141">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="f273c-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="f273c-142">В области данных отчета нажмите кнопку **создать**, а затем выберите **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="f273c-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="f273c-143">Убедитесь в том, что источником данных является **TextDataSource**.</span><span class="sxs-lookup"><span data-stu-id="f273c-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="f273c-144">В поле **Имя** введите **TextDataset**.</span><span class="sxs-lookup"><span data-stu-id="f273c-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="f273c-145">Убедитесь, что выбран тип запроса **Текст** , и нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="f273c-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="f273c-146">Нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="f273c-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="f273c-147">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="f273c-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="f273c-148">Чтобы запустить запрос, нажмите кнопку "Выполнить" (**!**).</span><span class="sxs-lookup"><span data-stu-id="f273c-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="f273c-149">Результаты запроса — это данные, доступные для отображения в отчете.</span><span class="sxs-lookup"><span data-stu-id="f273c-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="f273c-150">Добавление поля в отчет область конструктора</span><span class="sxs-lookup"><span data-stu-id="f273c-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="f273c-151">Когда необходимо добавить поле из набора данных в отчет, пользователю может показаться, что можно просто перетащить его непосредственно в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="f273c-152">В этом упражнении будет показано, почему этот способ не работает и что нужно делать вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f273c-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="f273c-153">Добавление поля в отчет (и получение неправильного результата)</span><span class="sxs-lookup"><span data-stu-id="f273c-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="f273c-154">Перетащите поле **FullName** из области данных отчета в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="f273c-155">Построитель отчетов создает текстовое поле с выражением, представленным как \<Expr>.</span><span class="sxs-lookup"><span data-stu-id="f273c-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="f273c-156">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="f273c-157">Обратите внимание, что существует только одна запись, **Фернандо Росс (**, которая в алфавитном порядке является первой записью в запросе.</span><span class="sxs-lookup"><span data-stu-id="f273c-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="f273c-158">Поле не повторяется и не показывает другие записи.</span><span class="sxs-lookup"><span data-stu-id="f273c-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="f273c-159">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="f273c-160">Выберите выражение \<Expr> в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="f273c-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="f273c-161">На панели "Свойства" напротив свойства **Значение** видно следующее (если панель "Свойства" не видна, на вкладке **Вид** установите флажок **Свойства**):</span><span class="sxs-lookup"><span data-stu-id="f273c-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="f273c-162">Функция `First` создана для извлечения только первого значения в поле, именно это и было сделано.</span><span class="sxs-lookup"><span data-stu-id="f273c-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="f273c-163">В результате перетаскивания поля непосредственно в область конструктора было создано текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="f273c-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="f273c-164">Текстовые поля сами по себе не являются областями данных, поэтому они не отображают данные из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="f273c-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="f273c-165">Текстовые поля в областях данных, такие как таблицы, матрицы и списки, не отображают данные.</span><span class="sxs-lookup"><span data-stu-id="f273c-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="f273c-166">Выберите текстовое поле (если выражение выбрано, нажмите клавишу ESC для выбора текстового поля) и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="f273c-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="f273c-167">Добавление поля в отчет (и получение правильного результата)</span><span class="sxs-lookup"><span data-stu-id="f273c-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="f273c-168">На ленте на вкладке **Вставка** в области **Области данных** выберите **Список**.</span><span class="sxs-lookup"><span data-stu-id="f273c-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="f273c-169">Щелкните область конструктора и перетащите курсор мыши, чтобы создать прямоугольник шириной 2 дюйма и высотой один дюйм.</span><span class="sxs-lookup"><span data-stu-id="f273c-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="f273c-170">Перетащите поле **FullName** из области данных отчета в поле списка.</span><span class="sxs-lookup"><span data-stu-id="f273c-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="f273c-171">В этот раз построитель отчетов создает текстовое поле с выражением `[FullName]` .</span><span class="sxs-lookup"><span data-stu-id="f273c-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="f273c-172">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="f273c-173">Обратите внимание, что в этот раз поле повторяется и показывает все записи запроса.</span><span class="sxs-lookup"><span data-stu-id="f273c-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="f273c-174">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="f273c-175">Выберите выражение в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="f273c-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="f273c-176">На панели "Свойства" у свойства **Значение** вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="f273c-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="f273c-177">Чтобы отобразить данные из набора данных, перетащите текстовое поле в область списка данных.</span><span class="sxs-lookup"><span data-stu-id="f273c-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="f273c-178">Выберите поле списка и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="f273c-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="f273c-179">Добавление таблицы в отчет область конструктора</span><span class="sxs-lookup"><span data-stu-id="f273c-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="f273c-180">Создайте таблицу, чтобы получить место для размещения гиперссылок и повернутого текста.</span><span class="sxs-lookup"><span data-stu-id="f273c-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="f273c-181">Добавление таблицы в отчет</span><span class="sxs-lookup"><span data-stu-id="f273c-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="f273c-182">В меню **Вставка** выберите пункт **Таблица**, а затем выберите пункт **Мастер таблиц**.</span><span class="sxs-lookup"><span data-stu-id="f273c-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="f273c-183">На странице **Выбор набора данных** мастера создания таблицы или матрицы щелкните **выбрать существующий набор данных в этом отчете или общий набор данных**, а затем щелкните **TextDataset (в этом отчете)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f273c-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f273c-184">На странице **Размещение полей** перетащите поля **территория**, **LinkText**и **Product** в **группы строк**, перетащите поле **Sales** в **значения**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f273c-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f273c-185">На странице **Выбор макета** снимите флажок **Развернуть/свернуть группы** , чтобы можно было увидеть всю таблицу, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f273c-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="f273c-186">На странице **Выбор стиля** щелкните элемент **содержание**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f273c-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="f273c-187">Перетащите таблицу так, чтобы она была ниже блока заголовка.</span><span class="sxs-lookup"><span data-stu-id="f273c-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="f273c-188">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="f273c-189">Таблица выглядит правильно, однако имеет две итоговые строки.</span><span class="sxs-lookup"><span data-stu-id="f273c-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="f273c-190">Для поля **LinkText** не требуется строка итогов.</span><span class="sxs-lookup"><span data-stu-id="f273c-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="f273c-191">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="f273c-192">Щелкните правой кнопкой мыши текстовое поле, содержащее `[LinkText]` , и выберите пункт **разбить ячейки**.</span><span class="sxs-lookup"><span data-stu-id="f273c-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="f273c-193">Выберите пустую ячейку под `[LinkText]` ячейкой, а затем нажмите и удерживайте клавишу Shift и выберите две ячейки справа: ячейка **итога** в столбце **продукт** и `[Sum(Sales)]` ячейка в столбце **продажи** .</span><span class="sxs-lookup"><span data-stu-id="f273c-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="f273c-194">Выбрав эти три ячейки, щелкните правой кнопкой мыши одну из этих ячеек и выберите команду **Удалить строку**.</span><span class="sxs-lookup"><span data-stu-id="f273c-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="f273c-195">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="f273c-196">Добавление гиперссылки в отчет</span><span class="sxs-lookup"><span data-stu-id="f273c-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="f273c-197">В этом разделе будет показано добавление гиперссылки в текст таблицы из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="f273c-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="f273c-198">Добавление гиперссылки на отчет</span><span class="sxs-lookup"><span data-stu-id="f273c-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="f273c-199">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f273c-200">Щелкните правой кнопкой мыши ячейку, содержащую `[LinkText]`, и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="f273c-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="f273c-201">В поле **Свойства текстового поля** выберите **действие**.</span><span class="sxs-lookup"><span data-stu-id="f273c-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="f273c-202">Щелкните **Переход к URL-адресу**.</span><span class="sxs-lookup"><span data-stu-id="f273c-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="f273c-203">В поле **Выбор URL-адреса** щелкните **[URL-адрес]**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f273c-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f273c-204">Обратите внимание, что текст ничем не отличается.</span><span class="sxs-lookup"><span data-stu-id="f273c-204">Note that the text does not look any different.</span></span> <span data-ttu-id="f273c-205">Необходимо сделать так, чтобы текст выглядел как текст ссылки.</span><span class="sxs-lookup"><span data-stu-id="f273c-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="f273c-206">Выберите `[LinkText]`.</span><span class="sxs-lookup"><span data-stu-id="f273c-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="f273c-207">В разделе **Шрифт** на вкладке **Главная** нажмите кнопку **Подчеркнутый** , а затем щелкните стрелку раскрывающегося списка рядом с кнопкой **Цвет** и выберите **синий цвет**.</span><span class="sxs-lookup"><span data-stu-id="f273c-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="f273c-208">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="f273c-209">Теперь текст выглядит как ссылка.</span><span class="sxs-lookup"><span data-stu-id="f273c-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="f273c-210">Щелкните ссылку.</span><span class="sxs-lookup"><span data-stu-id="f273c-210">Click a link.</span></span> <span data-ttu-id="f273c-211">Если компьютер подключен к Интернету, браузер откроет раздел справки построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="f273c-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="f273c-212">Поворот текста в отчете</span><span class="sxs-lookup"><span data-stu-id="f273c-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="f273c-213">В этом разделе будет показано вращение выбранного текста таблицы из предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="f273c-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="f273c-214">Вращение текста</span><span class="sxs-lookup"><span data-stu-id="f273c-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="f273c-215">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f273c-216">Щелкните ячейку, содержащую `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="f273c-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="f273c-217">На вкладке **Главная** в разделе **Шрифт** нажмите кнопку **Полужирный** .</span><span class="sxs-lookup"><span data-stu-id="f273c-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="f273c-218">Если панель свойств не открыта, перейдите на вкладку **Вид** и установите флажок **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="f273c-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="f273c-219">На панели свойств откройте свойство WritingMode.</span><span class="sxs-lookup"><span data-stu-id="f273c-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f273c-220">Если свойства на панели свойств упорядочены по категориям, свойство WritingMode относится к категории **Локализация** .</span><span class="sxs-lookup"><span data-stu-id="f273c-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="f273c-221">Убедитесь, что выбрана ячейка, а не текст.</span><span class="sxs-lookup"><span data-stu-id="f273c-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="f273c-222">WritingMode является свойством текстового поля, а не текста.</span><span class="sxs-lookup"><span data-stu-id="f273c-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="f273c-223">В списке щелкните **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="f273c-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="f273c-224">На вкладке **Главная** в разделе **абзац** щелкните кнопки **середина** и **Центральная** , чтобы нахождение текста в центре ячейки как по вертикали, так и по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="f273c-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="f273c-225">Нажмите кнопку Запустить (**!**).</span><span class="sxs-lookup"><span data-stu-id="f273c-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="f273c-226">Теперь текст в ячейке `[Territory]` располагается вертикально снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="f273c-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="f273c-227">Отображение текста с форматированием HTML</span><span class="sxs-lookup"><span data-stu-id="f273c-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="f273c-228">Отображение текста в формате HTML</span><span class="sxs-lookup"><span data-stu-id="f273c-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="f273c-229">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="f273c-230">На вкладке **Вставка** нажмите **Текстовое поле**, а затем в области конструктора щелкните и перетащите указатель мыши так, чтобы создать текстовое поле под таблицей примерно десять сантиметров шириной и семь с половиной сантиметров высотой.</span><span class="sxs-lookup"><span data-stu-id="f273c-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="f273c-231">Скопируйте этот текст и вставьте его в текстовое поле:</span><span class="sxs-lookup"><span data-stu-id="f273c-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="f273c-232">Выберите весь текст в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="f273c-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="f273c-233">Это свойство текста, а не текстового поля, поэтому в одном текстовом поле может находиться как простой текст, так и HTML-разметка для обозначения стилей.</span><span class="sxs-lookup"><span data-stu-id="f273c-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="f273c-234">Щелкните правой кнопкой мыши весь выделенный текст и выберите пункт **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="f273c-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="f273c-235">На странице **Общие** в разделе **тип разметки**щелкните **HTML — интерпретировать HTML-теги как стили**.</span><span class="sxs-lookup"><span data-stu-id="f273c-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="f273c-236">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f273c-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f273c-237">Нажмите кнопку "Выполнить" (**!**) для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="f273c-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="f273c-238">Текст в текстовом поле отображается как заголовок, абзац и маркированный список.</span><span class="sxs-lookup"><span data-stu-id="f273c-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="f273c-239">Формат валюты</span><span class="sxs-lookup"><span data-stu-id="f273c-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="f273c-240">Форматирование чисел в формате валюты</span><span class="sxs-lookup"><span data-stu-id="f273c-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="f273c-241">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="f273c-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="f273c-242">Щелкните верхнюю ячейку таблицы, содержащую `[Sum(Sales)]`, и, удерживая клавишу SHIFT, нажмите нижнюю ячейку таблицы, содержащую `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="f273c-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="f273c-243">На вкладке **Главная** в группе **Число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="f273c-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="f273c-244">Используемых На вкладке **Главная** в группе **число** нажмите кнопку **Стили заполнителя** и нажмите кнопку **выборка значений** , чтобы увидеть, как будут отформатированы числа.</span><span class="sxs-lookup"><span data-stu-id="f273c-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="f273c-245">На вкладке **Главная** в группе **Число** нажмите два раза кнопку **Уменьшить разрядность** , чтобы суммы в долларах отображались без центов (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f273c-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="f273c-246">Нажмите кнопку "Выполнить" (**!**) для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="f273c-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="f273c-247">Теперь отчет содержит форматированные данные и более удобен для чтения.</span><span class="sxs-lookup"><span data-stu-id="f273c-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="f273c-248">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="f273c-248">Save the Report</span></span>  
 <span data-ttu-id="f273c-249">Отчеты можно сохранять на сервере отчетов, в библиотеке SharePoint или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f273c-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="f273c-250">В данном учебнике предусмотрено сохранение отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="f273c-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="f273c-251">Если нет доступа к серверу отчетов, сохраните отчет на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f273c-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="f273c-252">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="f273c-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="f273c-253">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="f273c-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f273c-254">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="f273c-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="f273c-255">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="f273c-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="f273c-256">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="f273c-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="f273c-257">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="f273c-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="f273c-258">В поле **Имя**замените имя по умолчанию на произвольное имя.</span><span class="sxs-lookup"><span data-stu-id="f273c-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="f273c-259">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="f273c-260">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="f273c-260">The report is saved to the report server.</span></span> <span data-ttu-id="f273c-261">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="f273c-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="f273c-262">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="f273c-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="f273c-263">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="f273c-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f273c-264">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="f273c-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="f273c-265">В поле **Имя**замените имя по умолчанию на произвольное имя.</span><span class="sxs-lookup"><span data-stu-id="f273c-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="f273c-266">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f273c-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f273c-267">Next Steps</span><span class="sxs-lookup"><span data-stu-id="f273c-267">Next Steps</span></span>  
 <span data-ttu-id="f273c-268">Существует множество способов форматирования текста в построитель отчетов [руководстве. Создание отчета в свободной форме &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) содержит дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="f273c-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f273c-269">См. также:</span><span class="sxs-lookup"><span data-stu-id="f273c-269">See Also</span></span>  
 <span data-ttu-id="f273c-270">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="f273c-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="f273c-271">[Форматирование элементов отчета &#40;построитель отчетов и SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f273c-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f273c-272">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f273c-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
