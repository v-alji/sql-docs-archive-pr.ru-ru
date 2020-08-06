---
title: Получение данных из модели интеллектуального анализа данных (расширения интеллектуального анализа данных) (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- retrieving report data
- datasets [Reporting Services], with DMX queries
- datasets [Reporting Services], Analysis Services
- queries [Reporting Services], data mining prediction
ms.assetid: d9cd3624-1594-4707-8887-55437dd7e07c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a59184524967a9bfe772e41890afc3b900cc9e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738015"
---
# <a name="retrieve-data-from-a-data-mining-model-dmx-ssrs"></a><span data-ttu-id="de5b2-102">Получение данных из модели интеллектуального анализа данных (расширения интеллектуального анализа данных) (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="de5b2-102">Retrieve Data from a Data Mining Model (DMX) (SSRS)</span></span>
  <span data-ttu-id="de5b2-103">Для использования в отчете данных из модели интеллектуального анализа данных служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] необходимо определить источник данных служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] и один или несколько наборов данных отчета.</span><span class="sxs-lookup"><span data-stu-id="de5b2-103">To use data from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data mining model in your report, you must define a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source and one or more report datasets.</span></span> <span data-ttu-id="de5b2-104">При создании определения источника данных необходимо указать строку соединения и учетные данные, необходимые для осуществления доступа к источнику данных с компьютера клиента.</span><span class="sxs-lookup"><span data-stu-id="de5b2-104">When you create the data source definition, you must specify a connection string and credentials so that you can access the data source from your client computer.</span></span>  
  
 <span data-ttu-id="de5b2-105">Можно создать определение внедренного источника данных для использования в одном отчете или определение общего источника данных для использования в нескольких отчетах.</span><span class="sxs-lookup"><span data-stu-id="de5b2-105">You can create an embedded data source definition for use by a single report or a shared data source definition that can be used by multiple reports.</span></span> <span data-ttu-id="de5b2-106">Процедуры в этом разделе предназначены для создания внедренного источника данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-106">The procedures in this topic describe how to create an embedded data source.</span></span> <span data-ttu-id="de5b2-107">Дополнительные сведения об общих источниках данных см. в разделах [Внедренные и общие подключения к данным или источники данных (построитель отчетов и службы SSRS)](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) и [Создание, изменение и удаление общих источников данных (SSRS)](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de5b2-107">For more information about shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) and [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
 <span data-ttu-id="de5b2-108">После определения источника данных служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] можно создать один или несколько наборов данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-108">After you create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you can create one or more datasets.</span></span> <span data-ttu-id="de5b2-109">Для каждого из наборов данных следует использовать конструктор запросов прогноза интеллектуального анализа данных (расширения интеллектуального анализа данных), чтобы создать DMX-запрос, определяющий коллекцию полей.</span><span class="sxs-lookup"><span data-stu-id="de5b2-109">For each dataset, you use a Data Mining Prediction Expression (DMX) query designer to create a DMX query that specifies the field collection.</span></span> <span data-ttu-id="de5b2-110">Дополнительные сведения см. в статье [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="de5b2-110">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
 <span data-ttu-id="de5b2-111">Имя созданного набора данных появляется на панели «Данные отчета» в виде узла под соответствующим источником данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-111">After you create a dataset, the name of the dataset appears in the Report Data pane as a node under its data source.</span></span>  
  
 <span data-ttu-id="de5b2-112">После публикации отчета может понадобиться изменить учетные данные источника данных, чтобы разрешения, необходимые для получения данных при запуске отчета на сервере отчетов, были допустимыми.</span><span class="sxs-lookup"><span data-stu-id="de5b2-112">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
### <a name="to-create-an-embedded-microsoft-sql-server-analysis-services-data-source"></a><span data-ttu-id="de5b2-113">Создание внедренного источника данных служб Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="de5b2-113">To create an embedded Microsoft SQL Server Analysis Services data source</span></span>  
  
1.  <span data-ttu-id="de5b2-114">На панели инструментов в области данных отчета нажмите кнопку **Создать**и выберите **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-114">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="de5b2-115">В диалоговом окне **Свойства источника данных** в текстовое поле **Имя** введите имя или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de5b2-115">In the **Data Source Properties** dialog box, type a name in the **Name** text box, or accept the default name.</span></span>  
  
3.  <span data-ttu-id="de5b2-116">Убедитесь, что выбран параметр **Внедренное соединение** .</span><span class="sxs-lookup"><span data-stu-id="de5b2-116">Verify that **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="de5b2-117">В раскрывающемся списке **Тип** выберите пункт **Службы Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-117">From the **Type** drop-down list, select **Microsoft SQL Server Analysis Services**.</span></span>  
  
5.  <span data-ttu-id="de5b2-118">Укажите строку соединения, соответствующую источнику данных служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de5b2-118">Specify a connection string that works with your [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
     <span data-ttu-id="de5b2-119">Данные для строки соединения и учетные данные для подключения к источнику данных можно получить у администратора базы данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-119">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="de5b2-120">Ниже приведен пример строки соединения для образца базы данных [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] на локальном клиенте.</span><span class="sxs-lookup"><span data-stu-id="de5b2-120">The following connection string example specifies the sample [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] database on the local client.</span></span>  
  
    ```  
    Data Source=localhost;Initial Catalog=AdventureWorksDW2012  
    ```  
  
6.  <span data-ttu-id="de5b2-121">Нажмите кнопку **Учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-121">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="de5b2-122">Введите учетные данные, используемые для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-122">Set the credentials to use to connect to the data source.</span></span> <span data-ttu-id="de5b2-123">Дополнительные сведения см. в статье [Задание учетных данных и сведениях о соединении для источников данных отчета](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="de5b2-123">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de5b2-124">Чтобы проверить соединение с источником данных, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-124">To test the data source connection, click **Edit**.</span></span> <span data-ttu-id="de5b2-125">В диалоговом окне **Свойства соединения** нажмите кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-125">In the **Connection Properties** dialog box, click **Test Connection**.</span></span> <span data-ttu-id="de5b2-126">Если проверка прошла успешно, появится информационное сообщение: «Проверка соединения завершилась успешно».</span><span class="sxs-lookup"><span data-stu-id="de5b2-126">If the test is successful, you will see the information message "Test connection succeeded."</span></span> <span data-ttu-id="de5b2-127">Если проверка не прошла, появится предупреждающее сообщение с дополнительной информацией о причинах ошибки.</span><span class="sxs-lookup"><span data-stu-id="de5b2-127">If the test fails, you will see a warning message with more information about why the test was not successful.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="de5b2-128">Источник данных появится в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="de5b2-128">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-a-dataset-for-a-microsoft-sql-server-analysis-services"></a><span data-ttu-id="de5b2-129">Создание набора данных для служб Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="de5b2-129">To create a dataset for a Microsoft SQL Server Analysis Services</span></span>  
  
1.  <span data-ttu-id="de5b2-130">В области **Данные отчета** щелкните правой кнопкой мыши имя источника данных, который соединяется с источником данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], и выберите **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-130">In the **Report Data** pane, right-click the name of the data source that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="de5b2-131">В диалоговом окне **Свойства набора данных** введите имя в текстовое поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="de5b2-131">In the **Dataset Properties** dialog box, type a name in the **Name** text box.</span></span>  
  
3.  <span data-ttu-id="de5b2-132">В поле **Источник данных**убедитесь, что указанное имя является именем источника данных, соединяющегося со службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de5b2-132">In the **Data source box**, verify that the name is the name of a data source that connects to an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
4.  <span data-ttu-id="de5b2-133">Нажмите кнопку **Конструктор запросов** , чтобы открыть графический конструктор запросов для интерактивного построения запроса.</span><span class="sxs-lookup"><span data-stu-id="de5b2-133">Click **Query Designer** to open the graphical query designer to build a query interactively.</span></span> <span data-ttu-id="de5b2-134">Если конструктор запросов откроется в режиме многомерных выражений (MDX), нажмите на панели инструментов кнопку **Расширения интеллектуального анализа данных командного типа** (![Переключение в режим DMX-запросов](../media/rsqdicon-commandtypedmx.gif "Переключение в режим языка DMX-запросов")), чтобы переключиться на конструктор запросов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-134">If the query designer opens in MDX mode, click **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) on the toolbar to switch to the data mining query designer.</span></span> <span data-ttu-id="de5b2-135">Дополнительные сведения см. в статье [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="de5b2-135">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
     <span data-ttu-id="de5b2-136">Либо, чтобы импортировать существующий запрос расширений интеллектуального анализа данных из другого отчета, нажмите кнопку **Импорт**и перейдите к RDL-файлу, содержащему запрос.</span><span class="sxs-lookup"><span data-stu-id="de5b2-136">Alternatively, to import an existing DMX query from another report, click **Import**, and then navigate to the .rdl file with the DMX query.</span></span> <span data-ttu-id="de5b2-137">Импорт запросов из DMX-файлов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="de5b2-137">Importing a query from an .dmx file is not supported.</span></span>  
  
5.  <span data-ttu-id="de5b2-138">Для просмотра образца результатов после создания и выполнения запроса нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de5b2-138">After you create and run your query to see sample results, click **OK**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="de5b2-139">Набор данных и его коллекция полей появляются в области данных отчета под узлом источника данных.</span><span class="sxs-lookup"><span data-stu-id="de5b2-139">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5b2-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="de5b2-140">See Also</span></span>  
 <span data-ttu-id="de5b2-141">[Тип соединения служб Analysis Services для расширений интеллектуального анализа данных (службы SSRS)](analysis-services-connection-type-for-dmx-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de5b2-141">[Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span></span>  
 <span data-ttu-id="de5b2-142">[Подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="de5b2-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="de5b2-143">[Коллекция полей набора данных (построитель отчетов и службы SSRS)](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de5b2-143">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="de5b2-144">Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="de5b2-144">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
