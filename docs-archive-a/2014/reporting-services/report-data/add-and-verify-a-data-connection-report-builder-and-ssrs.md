---
title: Добавление и проверка подключения к данным или источника данных (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654859"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="c3a2a-102">Добавление и проверка подключения к данным или источнику данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c3a2a-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c3a2a-103">В построителе отчетов можно добавить общий источник данных с сервера отчетов или создать внедренный источник данных для отчета.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="c3a2a-104">В конструкторе отчетов можно создавать общие или внедренные источники данных и развертывать их на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="c3a2a-105">Чтобы добавить к отчету общий источник данных, перейдите к серверу отчетов и выберите общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="c3a2a-106">Общий источник данных в отчете указывает на определение общего источника данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="c3a2a-107">Чтобы создать внедренный источник данных, необходимы сведения о соединении с внешним источником данных и сведения о разрешениях для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="c3a2a-108">Эти сведения обычно предоставляет владелец источника данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="c3a2a-109">Можно проверить соединение, чтобы убедиться, что указаны правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="c3a2a-110">Дополнительные сведения см. в разделе [подключения к данным, источники данных и строки подключения в построитель отчетов](../data-connections-data-sources-and-connection-strings-in-report-builder.md) и [укажите учетные данные в построитель отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c3a2a-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="c3a2a-111">Создание ссылки на общий источник данных</span><span class="sxs-lookup"><span data-stu-id="c3a2a-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="c3a2a-112">На панели инструментов в области данных отчета нажмите кнопку **Создать** и выберите **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="c3a2a-113">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="c3a2a-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c3a2a-114">В текстовое поле **Имя** введите имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3a2a-115">Это имя сохраняется в локальном определении отчета.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="c3a2a-116">Это имя не является именем общего источника данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="c3a2a-117">Выберите **Использовать общее соединение или модель отчета**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="c3a2a-118">Отобразится список недавно использованных общих источников данных и моделей отчета.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="c3a2a-119">Чтобы выбрать необходимый источник на сервере отчетов, нажмите кнопку **Просмотр** и перейдите к папке на сервере отчетов, где расположены общие источники данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="c3a2a-120">Выберите общий источник данных и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="c3a2a-121">Источник данных появится в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c3a2a-122">Создание внедренного источника данных</span><span class="sxs-lookup"><span data-stu-id="c3a2a-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c3a2a-123">На панели инструментов в области данных отчета нажмите кнопку **создать**, а затем выберите **источник данных**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="c3a2a-124">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="c3a2a-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c3a2a-125">В текстовом поле **Имя** введите имя источника данных или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="c3a2a-126">Убедитесь, что установлен флажок **Использовать соединение, внедренное в отчет** .</span><span class="sxs-lookup"><span data-stu-id="c3a2a-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="c3a2a-127">В раскрывающемся списке **Выберите тип соединения** выберите тип источника данных, например **Microsoft SQL Server** или **OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="c3a2a-128">Укажите строку соединения одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="c3a2a-129">Введите строку соединения непосредственно в текстовое поле **Строка подключения** .</span><span class="sxs-lookup"><span data-stu-id="c3a2a-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="c3a2a-130">Список примеров строк подключения см. в разделе [Подключения к данным, источники данных и строки подключения в построителе отчетов](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c3a2a-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="c3a2a-131">Нажмите кнопку выражения **(fx)** , чтобы создать выражение, результатом которого является строка подключения.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="c3a2a-132">В диалоговом окне **Выражение** введите выражение на панели выражений.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="c3a2a-133">Нажмите кнопку **Построить** , чтобы открыть диалоговое окно **Свойства соединения** для типа источника данных, выбранного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="c3a2a-134">Заполните поля в диалоговом окне **Свойства соединения** , соответствующие этому типу источника данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="c3a2a-135">Свойства соединения включают тип и имя источника данных, а также учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="c3a2a-136">После указания значений в диалоговом окне, нажмите кнопку **Проверить соединение** , чтобы убедиться, что источник данных доступен и что заданные учетные данные правильны.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="c3a2a-137">Нажмите кнопку **Учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="c3a2a-138">Задайте учетные данные, которые будут использоваться с этим источником данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="c3a2a-139">Владелец источника данных выбирает тип поддерживаемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="c3a2a-140">В некоторых случаях владелец источника данных хранит общий источник данных на сервере отчетов и настраивает источник данных с учетными данными, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="c3a2a-141">Обратитесь за этими сведениями к владельцу источника данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="c3a2a-142">Дополнительные сведения см. в разделе [Указание учетных данных в построителе отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c3a2a-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="c3a2a-143">Источник данных появится в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="c3a2a-144">Проверка подключения к данным</span><span class="sxs-lookup"><span data-stu-id="c3a2a-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="c3a2a-145">На панели инструментов в области данных отчета дважды щелкните источник данных.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="c3a2a-146">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="c3a2a-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c3a2a-147">Нажмите кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="c3a2a-148">Если соединение установлено успешно, отображается следующее сообщение: "Соединение создано успешно".</span><span class="sxs-lookup"><span data-stu-id="c3a2a-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="c3a2a-149">Если установить соединение не удалось, отображается следующее сообщение: "Не удалось подключиться к источнику данных".</span><span class="sxs-lookup"><span data-stu-id="c3a2a-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="c3a2a-150">Нажмите кнопку **Подробные сведения**и воспользуйтесь предоставленными сведениями, чтобы исправить проблему.</span><span class="sxs-lookup"><span data-stu-id="c3a2a-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="c3a2a-151">Дополнительные сведения см. в разделе [Указание учетных данных в построителе отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c3a2a-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3a2a-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3a2a-152">See Also</span></span>  
 <span data-ttu-id="c3a2a-153">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c3a2a-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="c3a2a-154">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c3a2a-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c3a2a-155">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c3a2a-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c3a2a-156">Подключения к данным, источники данных и строки подключения в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="c3a2a-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
