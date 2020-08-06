---
title: 'Задача 4 (необязательно): объединение, сопоставление и публикация нового набора данных | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655458"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="ad291-102">Задача 4 (необязательно). Объединение, сопоставление и публикация нового набора данных</span><span class="sxs-lookup"><span data-stu-id="ad291-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="ad291-103">Со временем в репозиторий MDS потребуется добавить дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="ad291-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="ad291-104">Перед добавлением данных может оказаться полезным сравнить новые данные с данными, которые уже управляются в MDS, чтобы не добавлять дублирующиеся или неточные данные.</span><span class="sxs-lookup"><span data-stu-id="ad291-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="ad291-105">В надстройке служб Master Data Services для Excel можно объединять данные из двух листов, а также сравнивать данные для обнаружения и удаления повторений перед публикацией данных в MDS.</span><span class="sxs-lookup"><span data-stu-id="ad291-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="ad291-106">Функция сопоставления надстройки MDS для Excel использует функциональность сопоставления служб DQS для выявления совпадений в данных.</span><span class="sxs-lookup"><span data-stu-id="ad291-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="ad291-107">В этой задаче будет выполнено объединение данных из двух листов в один, а затем будет выполнено действие для выявления и удаления повторений перед публикацией в MDS.</span><span class="sxs-lookup"><span data-stu-id="ad291-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="ad291-108">Дополнительные сведения см. [в разделе Сопоставление качества данных в разделах надстройка MDS для Excel](https://msdn.microsoft.com/library/hh548681.aspx) и [Объединение данных](https://msdn.microsoft.com/library/hh548680.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ad291-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="ad291-109">Запуск нового экземпляра **Excel**.</span><span class="sxs-lookup"><span data-stu-id="ad291-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="ad291-110">Нажмите кнопку **Пуск**, наведите указатель на пункт **выполнить**, введите **Excel**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad291-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="ad291-111">Перейдите на вкладку **основные данные** , выбрав пункт **основные данные** в строке меню.</span><span class="sxs-lookup"><span data-stu-id="ad291-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="ad291-112">Нажмите кнопку **подключить** на ленте в группе **подключить и загрузить** , чтобы подключиться к **серверу MDS**.</span><span class="sxs-lookup"><span data-stu-id="ad291-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="ad291-113">Это соединение было настроено ранее на этом занятии.</span><span class="sxs-lookup"><span data-stu-id="ad291-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="ad291-114">![Excel — кнопка отображения обозревателя на вкладке основных данных](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel — кнопка отображения обозревателя на вкладке основных данных")</span><span class="sxs-lookup"><span data-stu-id="ad291-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="ad291-115">Справа появится область **Master обозреватель данных** .</span><span class="sxs-lookup"><span data-stu-id="ad291-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="ad291-116">Если мастер обозреватель данных не отображается, нажмите кнопку **Показать обозреватель** на ленте.</span><span class="sxs-lookup"><span data-stu-id="ad291-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="ad291-117">В окне **главный обозреватель данных** в раскрывающемся списке **модели**выберите **поставщики** .</span><span class="sxs-lookup"><span data-stu-id="ad291-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="ad291-118">Вы должны увидеть, что модель имеет одну сущность: **поставщик**.</span><span class="sxs-lookup"><span data-stu-id="ad291-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="ad291-119">![Excel — окно обозревателя основных данных](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel — окно обозревателя основных данных")</span><span class="sxs-lookup"><span data-stu-id="ad291-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="ad291-120">Дважды щелкните **поставщик** в списке сущностей, чтобы загрузить элементы сущности в лист Excel.</span><span class="sxs-lookup"><span data-stu-id="ad291-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="ad291-121">Щелкните элемент **Лист2** внизу, чтобы перейти на вкладку **Лист2** . Если вы не видите элемент **Лист2**, добавьте новый лист.</span><span class="sxs-lookup"><span data-stu-id="ad291-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="ad291-122">Откройте файл **Suppliers.xls** (исходный входной файл, который включен в файлы учебников) и скопируйте все (три) строки из листа **комбинеандклеансе** в **Лист2**.</span><span class="sxs-lookup"><span data-stu-id="ad291-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="ad291-123">Вернитесь к таблице **поставщиков** в **книге 1 — Microsoft Excel** (не **очищенный и сопоставленный список поставщиков** Excel), подключенный к **MDS**.</span><span class="sxs-lookup"><span data-stu-id="ad291-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="ad291-124">В строке меню щелкните **основные данные** .</span><span class="sxs-lookup"><span data-stu-id="ad291-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="ad291-125">Нажмите кнопку **объединить данные** на ленте.</span><span class="sxs-lookup"><span data-stu-id="ad291-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="ad291-126">Вы увидите диалоговое окно **Объединение данных** .</span><span class="sxs-lookup"><span data-stu-id="ad291-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="ad291-127">В диалоговом окне **Объединение данных** нажмите кнопку рядом с полем **диапазон для объединения с данными MDS** , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="ad291-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="ad291-128">![Excel — диалоговое окно «Объединение данных»](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel — диалоговое окно «Объединение данных»")</span><span class="sxs-lookup"><span data-stu-id="ad291-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="ad291-129">Теперь должно отобразиться свернутое диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ad291-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="ad291-130">Теперь нажмите кнопку **Лист2** , чтобы перейти на вкладку **Лист2** с данными о новом поставщике с 4 строками (включая одну строку заголовка).</span><span class="sxs-lookup"><span data-stu-id="ad291-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="ad291-131">На странице **Лист2**выберите **все строки, включая строку заголовка** (даже если они уже выбраны).</span><span class="sxs-lookup"><span data-stu-id="ad291-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="ad291-132">Вы увидите, что **диапазон для объединения с данными MDS** обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="ad291-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="ad291-133">![Excel — диалоговое окно «Объединение данных» — минимизировано](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel — диалоговое окно «Объединение данных» — минимизировано")</span><span class="sxs-lookup"><span data-stu-id="ad291-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="ad291-134">Вернитесь на вкладку **поставщики** , не закрывая диалоговое окно **Объединение данных** .</span><span class="sxs-lookup"><span data-stu-id="ad291-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="ad291-135">Нажмите кнопку **рядом с** **текстовым полем**.</span><span class="sxs-lookup"><span data-stu-id="ad291-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="ad291-136">Убедитесь, что диалоговое окно развернуто.</span><span class="sxs-lookup"><span data-stu-id="ad291-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="ad291-137">Вы увидите, что все сопоставления столбцов **сущности** MDS **поставщика** с столбцами **Excel** заполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="ad291-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="ad291-138">![Excel — диалоговое окно «Объединение данных» с данными](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel — диалоговое окно «Объединение данных» с данными")</span><span class="sxs-lookup"><span data-stu-id="ad291-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="ad291-139">Убедитесь, что столбец сущности **кода** сопоставлен со столбцом « **КодПоставщика** » на листе, а столбец сущности « **почтовый** индекс» сопоставлен со столбцом « **почтовый** индекс» на листе.</span><span class="sxs-lookup"><span data-stu-id="ad291-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="ad291-140">В диалоговом окне **Объединение данных** нажмите кнопку **объединить**.</span><span class="sxs-lookup"><span data-stu-id="ad291-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="ad291-141">Убедитесь, что 3 строки данных были помещены в конец листа. Они должны быть выделены цветом.</span><span class="sxs-lookup"><span data-stu-id="ad291-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="ad291-142">![Excel — новые элементы после объединения](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel — новые элементы после объединения")</span><span class="sxs-lookup"><span data-stu-id="ad291-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="ad291-143">Щелкните **математические данные** на ленте, чтобы выделить дубликаты.</span><span class="sxs-lookup"><span data-stu-id="ad291-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="ad291-144">Эта функция использует функции сопоставления служб DQS.</span><span class="sxs-lookup"><span data-stu-id="ad291-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="ad291-145">В диалоговом окне **сопоставление данных** выберите **поставщики** для **базы знаний DQS**.</span><span class="sxs-lookup"><span data-stu-id="ad291-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="ad291-146">![Excel — диалоговое окно «Сопоставление данных»](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel — диалоговое окно «Сопоставление данных»")</span><span class="sxs-lookup"><span data-stu-id="ad291-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="ad291-147">Сопоставьте столбцы листа с доменами, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ad291-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="ad291-148">Столбец листа</span><span class="sxs-lookup"><span data-stu-id="ad291-148">Worksheet Column</span></span>|<span data-ttu-id="ad291-149">Домен</span><span class="sxs-lookup"><span data-stu-id="ad291-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="ad291-150">Code (Supplier ID был загружен как Code для сущности Supplier в MDS)</span><span class="sxs-lookup"><span data-stu-id="ad291-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="ad291-151">Supplier ID</span><span class="sxs-lookup"><span data-stu-id="ad291-151">Supplier ID</span></span>|  
    |<span data-ttu-id="ad291-152">Name (Supplier Name было загружено как Name для сущности Supplier в MDS)</span><span class="sxs-lookup"><span data-stu-id="ad291-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="ad291-153">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="ad291-153">Supplier Name</span></span>|  
    |<span data-ttu-id="ad291-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="ad291-154">ContactEmailAddress</span></span>|<span data-ttu-id="ad291-155">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="ad291-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="ad291-156">Выберите **необходимый компонент** для сопоставления столбцов **кода** .</span><span class="sxs-lookup"><span data-stu-id="ad291-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="ad291-157">Введите **70%** в качестве **веса** для **имени поставщика** и **30%** в качестве **веса** для **контактного адреса электронной почты** , как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="ad291-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="ad291-158">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad291-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="ad291-159">Процесс сопоставления должен обозначать один дубликат для поставщика с **кодом: S1**.</span><span class="sxs-lookup"><span data-stu-id="ad291-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="ad291-160">![Excel — результаты сопоставления](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel — результаты сопоставления")</span><span class="sxs-lookup"><span data-stu-id="ad291-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="ad291-161">Выберите **повторяющуюся строку (оранжевый)**, щелкните ее правой кнопкой мыши и нажмите кнопку **Удалить** , чтобы удалить строку.</span><span class="sxs-lookup"><span data-stu-id="ad291-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="ad291-162">Удалите столбец **CLUSTER_ID** , так как он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="ad291-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="ad291-163">Щелкните **опубликовать** , чтобы опубликовать две новые записи с **кодами S66** и **S57** в MDS.</span><span class="sxs-lookup"><span data-stu-id="ad291-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="ad291-164">В диалоговом окне **Публикация и заметки** добавьте **заметку**и нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="ad291-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="ad291-165">Переключитесь на **Диспетчер основных данных веб-приложение**.</span><span class="sxs-lookup"><span data-stu-id="ad291-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="ad291-166">На домашней странице убедитесь, что для **модели**выбраны **поставщики** , и нажмите кнопку **Обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="ad291-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="ad291-167">Если **Обозреватель** уже открыт, обновите веб – браузер.</span><span class="sxs-lookup"><span data-stu-id="ad291-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="ad291-168">**Отсортируйте** список по **коду** и ищите записи с **S57** и **S66** в виде кодов.</span><span class="sxs-lookup"><span data-stu-id="ad291-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="ad291-169">Можно также использовать кнопку **Фильтр** на панели инструментов для поиска конкретной записи в списке.</span><span class="sxs-lookup"><span data-stu-id="ad291-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="ad291-170">Теперь закройте окно **book1 — Microsoft Excel** без сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="ad291-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ad291-171">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ad291-171">Next Step</span></span>  
 [<span data-ttu-id="ad291-172">Задача 5. Создание атрибута на основе домена в Excel</span><span class="sxs-lookup"><span data-stu-id="ad291-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
