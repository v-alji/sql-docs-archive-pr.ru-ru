---
title: Использование подключения к данным Office (ODC) с отчетами (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Office Data Connection (.odc) files
- SharePoint integration [Reporting Services], shared data sources
- .odc files
ms.assetid: e8d6896d-f886-4390-8b5d-96f0a50c250c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d795c46f46b45511079ac03add2d18214ac54489
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654821"
---
# <a name="use-an-office-data-connection-odc-with-reports-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="4507a-102">Использование ODC-файла подключения к данным Office в отчетах (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4507a-102">Use an Office Data Connection (.odc) with Reports (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="4507a-103">В некоторых случаях для предоставления в отчет служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] сведений о соединении можно использовать существующий ODC-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-103">For limited scenarios, you can use an existing Office Data Connection (.odc) file to provide connection information to a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report.</span></span> <span data-ttu-id="4507a-104">ODC-файл может быть использован вместо RSDS-файла при создании общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="4507a-104">An .odc file can be used in place of an .rsds file when you create a shared data source.</span></span> <span data-ttu-id="4507a-105">Сервер отчетов использует ODC-файл так же, как и RSDS-файлы. Он считывает из файла тип источника данных, строку соединения и сведения об учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4507a-105">The report server uses an .odc file in the same way it uses an .rsds file; it reads the file for the data source type, a connection string, and credential information.</span></span>  
  
 <span data-ttu-id="4507a-106">Не все ODC-файлы могут быть использованы в отчете служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4507a-106">Not all .odc files can be used with a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report.</span></span> <span data-ttu-id="4507a-107">Модуль обработки данных и характеристики отчета и ODC-файла определяют, можно ли использовать ODC-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-107">The data processing extension and characteristics of the report and .odc file determine whether an .odc can be used:</span></span>  
  
-   <span data-ttu-id="4507a-108">Отчет должен быть сконструирован для работы с поставщиком данных OLE DB или ODBC.</span><span class="sxs-lookup"><span data-stu-id="4507a-108">The report must be designed to work with an OLE DB or ODBC data provider.</span></span> <span data-ttu-id="4507a-109">Если при создании отчета использовался другой модуль обработки данных, то отчет и входящие в него запросы могут включать возможности, не поддерживаемые поставщиками данных OLE DB или ODBC.</span><span class="sxs-lookup"><span data-stu-id="4507a-109">If you used a different data processing extension to create the report, the report or its queries might include functionality that is not supported by the OLE DB or ODBC data provider.</span></span>  
  
-   <span data-ttu-id="4507a-110">Используемый ODC-файл должен включать в себя необходимые элементы и иметь определенную структуру.</span><span class="sxs-lookup"><span data-stu-id="4507a-110">The .odc file must have the expected elements and structure.</span></span> <span data-ttu-id="4507a-111">Чтобы сервер отчетов мог считать параметры поставщика данных и учетные данные, их необходимо указывать в файле в явном виде.</span><span class="sxs-lookup"><span data-stu-id="4507a-111">The data provider and credential settings must be set explicitly in the file so that they can be read by the report server.</span></span> <span data-ttu-id="4507a-112">Лучший способ указания этих значений — экспорт ODC-файла перед передачей его в библиотеку SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4507a-112">The best way to set these values is to export the .odc file before uploading it to the SharePoint library.</span></span>  
  
-   <span data-ttu-id="4507a-113">ODC-файл должен содержать сведения о типе соединения OLE DB или ODBC.</span><span class="sxs-lookup"><span data-stu-id="4507a-113">The .odc file must specify a connection type of OLE DB or ODBC.</span></span>  
  
-   <span data-ttu-id="4507a-114">ODC-файл должен содержать строку соединения.</span><span class="sxs-lookup"><span data-stu-id="4507a-114">The .odc file must specify a connection string.</span></span>  
  
-   <span data-ttu-id="4507a-115">Учетные данные могут принимать значение `None`, `Stored` или `Integrated`.</span><span class="sxs-lookup"><span data-stu-id="4507a-115">Credentials can be set to `None`, `Stored`, or `Integrated`.</span></span> <span data-ttu-id="4507a-116">Если для учетных данных указан метод `Stored`, то сервер отчетов предлагает ввести их вместо использования сохраненных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4507a-116">If the credentials method is set to `Stored`, the report server will prompt the user for credentials instead of using the stored credentials.</span></span> <span data-ttu-id="4507a-117">Сервер отчетов не может использовать сохраненные учетные данные, как определено в ODC-файле.</span><span class="sxs-lookup"><span data-stu-id="4507a-117">The report server cannot use stored credentials as defined in the .odc file.</span></span>  
  
-   <span data-ttu-id="4507a-118">Схема источника данных должна совпадать со схемой, используемой при создании отчета.</span><span class="sxs-lookup"><span data-stu-id="4507a-118">The data source must have schema that is identical to the one used to create the report.</span></span> <span data-ttu-id="4507a-119">Если структуры данных различны, то отчет не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="4507a-119">If the data structures are different, the report will not run.</span></span>  
  
-   <span data-ttu-id="4507a-120">ODC-файл должен быть создан в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office 2007 (предыдущие версии ODC-файла не совместимы с файлами определений отчетов).</span><span class="sxs-lookup"><span data-stu-id="4507a-120">The .odc file must be created in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office 2007 (older versions of .odc are not compatible with report definition files).</span></span>  
  
 <span data-ttu-id="4507a-121">ODC-файлы нельзя использовать для указания соединений с источниками данных, которые не поддерживаются сервером отчетов, даже в тех случаях, когда типы данных, указанные в данных файлах, близки к поддерживаемым типам.</span><span class="sxs-lookup"><span data-stu-id="4507a-121">You cannot use .odc files that specify connections to data sources that cannot be processed on a report server, even if the .odc data source types look similar to supported data source types.</span></span> <span data-ttu-id="4507a-122">В частности, если ODC-файл был создан с помощью Microsoft Excel 2007, получающего данные из СУБД Microsoft Access, веб-узла или текстового файла, его нельзя использовать для предоставления данных в отчет.</span><span class="sxs-lookup"><span data-stu-id="4507a-122">Specifically, if you created an .odc file in Microsoft Excel 2007 that retrieves data from Microsoft Access, the Web, or a text file, you cannot use that .odc file to provide data to a report.</span></span>  
  
 <span data-ttu-id="4507a-123">Отчеты и модели построителя отчетов не поддерживают работу с ODC-файлами.</span><span class="sxs-lookup"><span data-stu-id="4507a-123">Report Builder reports and models do not work with .odc file.</span></span> <span data-ttu-id="4507a-124">ODC-файл не может быть использован для создания модели. В свою очередь, нельзя настраивать модель для использования общего источника данных, ссылающегося на ODC-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-124">You cannot use an .odc file to generate a model, and you cannot configure the model to use a shared data source that links to an .odc file.</span></span>  
  
 <span data-ttu-id="4507a-125">Представленные ниже инструкции могут быть использованы при создании и экспорте ODC-файлов.</span><span class="sxs-lookup"><span data-stu-id="4507a-125">If you are not familiar with .odc files, you can use the following instructions to create and export one.</span></span> <span data-ttu-id="4507a-126">Одним из простых способов создания ODC-файла для источника данных OLE DB является применение Excel 2007 и мастера подключений к данным.</span><span class="sxs-lookup"><span data-stu-id="4507a-126">One easy way to create an .odc file for an OLE DB data source is to use Excel 2007 and the Data Connection Wizard.</span></span> <span data-ttu-id="4507a-127">Заметим, что мастер не создает источник данных; необходим внешний источник данных, который уже определен.</span><span class="sxs-lookup"><span data-stu-id="4507a-127">Note that the wizard does not create a data source; you must have an external data source that is already defined.</span></span>  
  
 <span data-ttu-id="4507a-128">Существующий ODC-файл должен использоваться только в том случае, если он является полностью совместимым с отчетом и запросами.</span><span class="sxs-lookup"><span data-stu-id="4507a-128">An existing .odc file should only be used if it is fully compatible with the report and queries.</span></span> <span data-ttu-id="4507a-129">При возникновении ошибок, требующих серьезных изменений отчета или ODC-файла, необходимо создать для указанного отчета новый RSDS-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-129">If you run into errors that require significant modifications to either the report or to the .odc file, you should create a new .rsds file for the report.</span></span> <span data-ttu-id="4507a-130">Дополнительные сведения о создании общего источника данных, использующего RSDS-файл, см. в разделе [Создание общих источников данных и управление ими (службы Reporting Services в режиме интеграции с SharePoint)](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="4507a-130">For more information about how to create a shared data source that uses an .rsds file, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
### <a name="to-create-and-export-an-odc-file"></a><span data-ttu-id="4507a-131">Создание и экспорт ODC-файла</span><span class="sxs-lookup"><span data-stu-id="4507a-131">To create and export an .odc file</span></span>  
  
1.  <span data-ttu-id="4507a-132">Запустите Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="4507a-132">Start Excel 2007.</span></span>  
  
2.  <span data-ttu-id="4507a-133">На вкладке **Данные** в группе **Получение внешних данных** выберите **От других источников**, затем **От мастера подключения к данным**.</span><span class="sxs-lookup"><span data-stu-id="4507a-133">On the **Data** tab, in the **Get External Data** group, click **From Other Sources**, and then click **From Data Connection Wizard**.</span></span>  
  
3.  <span data-ttu-id="4507a-134">Выберите **Другое/Дополнительно**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4507a-134">Select **Other/Advanced**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="4507a-135">Выберите **Поставщик Microsoft OLE DB для SQL Server**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4507a-135">Select **Microsoft OLE DB Provider for SQL Server**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="4507a-136">Введите имя сервера (по умолчанию используется сетевое имя компьютера) и учетную запись пользователя, имеющего верное имя входа и разрешения на доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="4507a-136">Enter the name of the server (by default, it is the network name of the computer) and a user account that has a valid login and database permissions.</span></span> <span data-ttu-id="4507a-137">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4507a-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4507a-138">Выберите базу данных, затем нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Связь данных** .</span><span class="sxs-lookup"><span data-stu-id="4507a-138">Select a database, and then click **OK** to close the **Data Link** dialog box.</span></span>  
  
7.  <span data-ttu-id="4507a-139">По умолчанию флажок **Подключение к заданной таблице** установлен.</span><span class="sxs-lookup"><span data-stu-id="4507a-139">The **Connect to specific table** check box is selected by default.</span></span> <span data-ttu-id="4507a-140">Этот параметр используется для получения данных из заданной таблицы.</span><span class="sxs-lookup"><span data-stu-id="4507a-140">It is used to retrieve data from a specific table.</span></span> <span data-ttu-id="4507a-141">Сервер отчетов не обрабатывает запросы в ODC-файле. Поэтому состояние флажка не влияет на его работу.</span><span class="sxs-lookup"><span data-stu-id="4507a-141">The report server ignores all queries in an .odc file, so it does not matter whether you select or clear the check box.</span></span> <span data-ttu-id="4507a-142">Запросы, получающие данные для отчета, необходимо включать в файл определения отчета, а не во внешние файлы.</span><span class="sxs-lookup"><span data-stu-id="4507a-142">Queries that retrieve data for a report are included in a report definition file and not in external files.</span></span>  
  
8.  <span data-ttu-id="4507a-143">При открытом соединении можно изменять его параметры, а также экспортировать соединение.</span><span class="sxs-lookup"><span data-stu-id="4507a-143">While the connection is open, you can edit properties and export it.</span></span> <span data-ttu-id="4507a-144">На вкладке **Данные** в группе **Соединения** выберите **Свойства**, затем нажмите кнопку **Свойства соединения** , расположенную рядом с именем соединения.</span><span class="sxs-lookup"><span data-stu-id="4507a-144">On the **Data** tab, in the **Connections** group, click **Properties**, and then click the **Connection Properties** button next to the connection name.</span></span>  
  
9. <span data-ttu-id="4507a-145">На вкладке **Определение** нажмите кнопку **Экспорт файла соединения**.</span><span class="sxs-lookup"><span data-stu-id="4507a-145">On the **Definition** tab, click **Export Connection File**.</span></span>  
  
10. <span data-ttu-id="4507a-146">Введите имя файла и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4507a-146">Enter a name for the file, and then click **Save**.</span></span> <span data-ttu-id="4507a-147">Закройте приложение и все открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="4507a-147">Close the application and all open files.</span></span>  
  
### <a name="to-upload-and-use-an-odc-file"></a><span data-ttu-id="4507a-148">Передача и использование ODC-файла</span><span class="sxs-lookup"><span data-stu-id="4507a-148">To upload and use an .odc file</span></span>  
  
1.  <span data-ttu-id="4507a-149">Откройте библиотеку, в которую необходимо передать файл соединения.</span><span class="sxs-lookup"><span data-stu-id="4507a-149">Open the library into which you want to upload the connection file.</span></span>  
  
2.  <span data-ttu-id="4507a-150">В меню **Передача** выберите команду **Передать документ**.</span><span class="sxs-lookup"><span data-stu-id="4507a-150">On the **Upload** menu, click **Upload document**.</span></span>  
  
3.  <span data-ttu-id="4507a-151">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="4507a-151">Click **Browse**.</span></span>  
  
4.  <span data-ttu-id="4507a-152">Выделите созданный ранее ODC-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-152">Select the .odc file you created.</span></span> <span data-ttu-id="4507a-153">По умолчанию ODC-файл хранится в папке «Мои документы\Мои источники данных».</span><span class="sxs-lookup"><span data-stu-id="4507a-153">By default, the .odc file is in the My Documents folder, in My Data Sources.</span></span>  
  
5.  <span data-ttu-id="4507a-154">Чтобы выбрать файл, нажмите кнопку **Открыть** , затем нажмите кнопку **ОК** для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="4507a-154">Click **Open** to select the file, click **OK** to save the selection.</span></span> <span data-ttu-id="4507a-155">Автоматически откроется страница свойств нового элемента.</span><span class="sxs-lookup"><span data-stu-id="4507a-155">The properties page for the new item opens automatically.</span></span>  
  
6.  <span data-ttu-id="4507a-156">На вкладке «Тип содержимого» выберите **Источник данных отчета**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4507a-156">In Content Type, select **Report Data Source**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4507a-157">Укажите отчет.</span><span class="sxs-lookup"><span data-stu-id="4507a-157">Point to a report.</span></span>  
  
8.  <span data-ttu-id="4507a-158">Нажмите кнопку со стрелкой вниз и выберите **Управление источниками данных**.</span><span class="sxs-lookup"><span data-stu-id="4507a-158">Click the down arrow, and select **Manage Data Sources**.</span></span>  
  
9. <span data-ttu-id="4507a-159">Щелкните имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="4507a-159">Click the data source name.</span></span>  
  
10. <span data-ttu-id="4507a-160">Если в отчете используются данные пользовательского источника данных, выберите **Общий**.</span><span class="sxs-lookup"><span data-stu-id="4507a-160">If the report uses custom data source information, click **Shared**.</span></span>  
  
11. <span data-ttu-id="4507a-161">В окне **Связь с источниками данных**нажмите кнопку обзора ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="4507a-161">In **Data Source Link**, click the browse (**...**) button.</span></span>  
  
12. <span data-ttu-id="4507a-162">Выделите только что переданный ODC-файл.</span><span class="sxs-lookup"><span data-stu-id="4507a-162">Select the .odc file you just uploaded.</span></span>  
  
13. <span data-ttu-id="4507a-163">Нажмите кнопку **ОК** для выберите файл, а затем нажмите кнопку **ОК** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="4507a-163">Click **OK** to select the file, and then click **OK** to save your changes.</span></span>  
  
     <span data-ttu-id="4507a-164">Если представленные выше шаги применяются к образцу базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , необходимо иметь в виду, что полной совместимостью с ODC-файлом обладает только отчет Company Sales.</span><span class="sxs-lookup"><span data-stu-id="4507a-164">If you are trying these steps with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database and sample reports, be aware that only the Company Sales report will work out-of-the-box with an .odc file.</span></span> <span data-ttu-id="4507a-165">Другие образцы отчетов включают в себя параметры и функции запросов, не совместимые с поставщиком OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4507a-165">The other sample reports contain query parameters and features that do not work with the OLE DB provider.</span></span> <span data-ttu-id="4507a-166">Однако указанные отчеты можно преобразовать с помощью конструктора отчетов, после чего их можно будет использовать с поставщиком OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4507a-166">However, you can make the reports work with the OLE DB provider if you modify them first in Report Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4507a-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="4507a-167">See Also</span></span>  
 [<span data-ttu-id="4507a-168">Создание, изменение и удаление общих источников данных (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4507a-168">Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;</span></span>](create-modify-and-delete-shared-data-sources-ssrs.md)  
  
  
