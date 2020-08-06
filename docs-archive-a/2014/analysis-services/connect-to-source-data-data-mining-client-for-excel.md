---
title: Подключение к источнику данных (клиент интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656711"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="effbc-102">Подключение к источнику данных (клиент интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="effbc-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="effbc-103">В этом разделе описано, как создавать и использовать новые соединения, используемые для хранения моделей интеллектуального анализа данных, а также для доступа к внешним данным, хранящимся в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="effbc-104">**Подключения интеллектуального анализа данных.**</span><span class="sxs-lookup"><span data-stu-id="effbc-104">**Data mining connections.**</span></span> <span data-ttu-id="effbc-105">Созданное при запуске надстроек первоначальное соединение используется для доступа к алгоритмам, анализа данных и сохранения моделей и структур интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="effbc-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="effbc-106">Требуется подключение к экземпляру [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для использования средств визуализации и моделирования в надстройках, поскольку надстройки зависят от алгоритмов и структур данных, предоставляемых службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="effbc-107">**Подключения к внешним источникам данных.**</span><span class="sxs-lookup"><span data-stu-id="effbc-107">**Connections to external data sources.**</span></span> <span data-ttu-id="effbc-108">Можно также создавать подключения к внешним источникам данных при построении моделей или сохранении результатов.</span><span class="sxs-lookup"><span data-stu-id="effbc-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="effbc-109">Например, можно создать модель интеллектуального анализа данных на одном сервере, а затем выполнить прогнозирующий запрос к этой модели интеллектуального анализа данных, используя данные, хранимые на другом экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], в таблице Excel или во внешнем источнике данных, таком как [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span><span class="sxs-lookup"><span data-stu-id="effbc-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="effbc-110">Каждый раз при обращении к новому источнику данных будет появляться диалоговое окно с предложением создать соединение.</span><span class="sxs-lookup"><span data-stu-id="effbc-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="effbc-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="effbc-111">Prerequisites</span></span>  
 <span data-ttu-id="effbc-112">Эта версия надстройки требует, чтобы ваш экземпляр [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] был на основе SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="effbc-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="effbc-113">Если требуется подключиться к более ранней версии служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], имеется отдельная версия этих надстроек.</span><span class="sxs-lookup"><span data-stu-id="effbc-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="effbc-114">Существуют версии надстроек, которые поддерживают SQL Server 2005, SQL Server 2008 и SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="effbc-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="effbc-115">Чтобы установить соединение с базой данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], необходимо наличие разрешений на доступ к серверу баз данных.</span><span class="sxs-lookup"><span data-stu-id="effbc-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="effbc-116">Кроме того, необходимо включить сеансы интеллектуального анализа данных и иметь разрешения на чтение или чтение и запись объектов базы данных, сохраненных на сервере.</span><span class="sxs-lookup"><span data-stu-id="effbc-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="effbc-117">Создание подключений к серверу интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="effbc-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="effbc-118">Группа **соединений** в клиенте интеллектуального анализа данных для Excel и средства анализа таблиц для Excel предоставляет средства для управления соединениями с экземпляром служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="effbc-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="effbc-119">Можно создать соединение при установке надстройки или добавить его позже.</span><span class="sxs-lookup"><span data-stu-id="effbc-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="effbc-120">Можно создать несколько соединений и менять их в любое время, кроме случаев, когда запущен процесс создания или отправки запросов к модели.</span><span class="sxs-lookup"><span data-stu-id="effbc-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="effbc-121">Не изменяйте и не закрывайте подключение во время обработки модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="effbc-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="effbc-122">Модель интеллектуального анализа данных может потерять данные или стать непригодной для использования.</span><span class="sxs-lookup"><span data-stu-id="effbc-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="effbc-123">Только одно соединение может быть активно одновременно.</span><span class="sxs-lookup"><span data-stu-id="effbc-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="effbc-124">Соединения в надстройках Excel</span><span class="sxs-lookup"><span data-stu-id="effbc-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="effbc-125">Группа **Connections** в клиенте интеллектуального анализа данных для Excel и средства анализа таблиц для Excel — это место, где вы управляете соединениями с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="effbc-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="effbc-126">Создание нового соединения с сервером в надстройках Excel</span><span class="sxs-lookup"><span data-stu-id="effbc-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="effbc-127">Нажмите кнопку **Connection (соединение** ) на ленте **анализ** или **интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="effbc-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="effbc-128">Надпись на кнопке указывает наличие соединения.</span><span class="sxs-lookup"><span data-stu-id="effbc-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="effbc-129">Если на листе не установлено соединение, кнопка содержит текст " \<No connection> ." Если подключение было ранее установлено в книге, в кнопке появится имя этого соединения.</span><span class="sxs-lookup"><span data-stu-id="effbc-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="effbc-130">В диалоговом окне **Analysis Services соединения** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="effbc-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="effbc-131">В диалоговом окне **новое подключение Analysis Services** введите имя сервера.</span><span class="sxs-lookup"><span data-stu-id="effbc-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="effbc-132">Выберите метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="effbc-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="effbc-133">Выберите базу данных из раскрывающегося списка **имя каталога** .</span><span class="sxs-lookup"><span data-stu-id="effbc-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="effbc-134">Если на экземпляре не существует базы данных, выберите **значение (по умолчанию)**.</span><span class="sxs-lookup"><span data-stu-id="effbc-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="effbc-135">Введите понятное имя для соединения.</span><span class="sxs-lookup"><span data-stu-id="effbc-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="effbc-136">Нажмите кнопку **проверить подключение** , чтобы убедиться, что сервер и база данных доступны.</span><span class="sxs-lookup"><span data-stu-id="effbc-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="effbc-137">Нажмите кнопку **ОК**, затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="effbc-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="effbc-138">Соединения с использованием веб-службы</span><span class="sxs-lookup"><span data-stu-id="effbc-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="effbc-139">При использовании архитектуры тонкого клиента, разрешающей просмотр кубов и данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], можно также настроить соединение с сервером служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] с помощью веб-служб.</span><span class="sxs-lookup"><span data-stu-id="effbc-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="effbc-140">Дополнительные сведения об определении веб-клиента см. в электронной документации по [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="effbc-141">При наличии доступа к серверу, настроенному для веб-служб, тип соединения можно указать при первом создании соединения.</span><span class="sxs-lookup"><span data-stu-id="effbc-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="effbc-142">Создание HTTP-соединения со службами Analysis Services</span><span class="sxs-lookup"><span data-stu-id="effbc-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="effbc-143">Откройте диалоговое окно **Создание соединения Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="effbc-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="effbc-144">В качестве имени введите http:// и URL-адрес сервера служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="effbc-145">Введите имя пользователя и пароль, необходимые для доступа к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="effbc-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="effbc-146">Соединения в надстройке Visio</span><span class="sxs-lookup"><span data-stu-id="effbc-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="effbc-147">В отличие от Excel, программа Visio не содержит ленты средств и кнопок, специально предназначенных для создания и наблюдения за соединением.</span><span class="sxs-lookup"><span data-stu-id="effbc-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="effbc-148">Вместо этого подключение к данным создается при первоначальном выборе фигуры интеллектуального анализа данных и перетаскивании ее на страницу Visio.</span><span class="sxs-lookup"><span data-stu-id="effbc-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="effbc-149">Мастер предложит выбрать модель для фигуры и задать другие параметры.</span><span class="sxs-lookup"><span data-stu-id="effbc-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="effbc-150">Если ранее использовались соединения с источниками данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в Excel, эти соединения будут перечислены в списке источников данных для выбора.</span><span class="sxs-lookup"><span data-stu-id="effbc-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="effbc-151">Создание соединения для фигуры Visio</span><span class="sxs-lookup"><span data-stu-id="effbc-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="effbc-152">Откройте шаблон интеллектуального анализа данных и выберите одну из фигур интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="effbc-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="effbc-153">Перетащите эту фигуру на пустую страницу.</span><span class="sxs-lookup"><span data-stu-id="effbc-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="effbc-154">В диалоговом окне **Выбор источника данных** выберите из списка источник данных или нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="effbc-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="effbc-155">Если выбран вариант **создать**, выполните процедуру, описанную выше, чтобы указать имя сервера и каталога или подключиться через веб-службу.</span><span class="sxs-lookup"><span data-stu-id="effbc-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="effbc-156">Изменение подключений</span><span class="sxs-lookup"><span data-stu-id="effbc-156">Changing Connections</span></span>  
 <span data-ttu-id="effbc-157">Можно создать несколько соединений на одном листе, но одновременно может быть активно только одно соединение.</span><span class="sxs-lookup"><span data-stu-id="effbc-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="effbc-158">Имя текущего соединения отображается в кнопке **Подключение** .</span><span class="sxs-lookup"><span data-stu-id="effbc-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="effbc-159">В клиенте интеллектуального анализа данных для Excel можно также проверить строку подключения и состояние текущего соединения, щелкнув **Трассировка** , а затем выбрав **текущее соединение**.</span><span class="sxs-lookup"><span data-stu-id="effbc-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="effbc-160">Используйте другое соединение с сервером</span><span class="sxs-lookup"><span data-stu-id="effbc-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="effbc-161">Щелкните **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="effbc-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="effbc-162">В области **подключения Analysis Services** выберите соединение из списка **другие подключения** и щелкните **сделать текущим**.</span><span class="sxs-lookup"><span data-stu-id="effbc-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="effbc-163">Нажмите кнопку **проверить подключение** , чтобы убедиться, что подключение доступно.</span><span class="sxs-lookup"><span data-stu-id="effbc-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="effbc-164">После завершения обработки модели интеллектуального анализа данных результаты сохраняются на локальном компьютере и на них не повлияет завершение соединения с одним сервером и подключение к другому.</span><span class="sxs-lookup"><span data-stu-id="effbc-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="effbc-165">Однако надо избегать смены или завершения соединения во время обработки модели интеллектуального анализа данных, так как это может повредить данные.</span><span class="sxs-lookup"><span data-stu-id="effbc-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="effbc-166">Изменение существующего соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="effbc-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="effbc-167">Нельзя изменить существующее соединение. Если необходимо подключиться к другой базе данных или к другому серверу, необходимо создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="effbc-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="effbc-168">Если необходимо изменить строку подключения, чтобы увеличить время ожидания запроса или добавить другие параметры, относящиеся к экземпляру [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], одно из возможных решений — изменить DMC-файл, в котором хранится строка подключения.</span><span class="sxs-lookup"><span data-stu-id="effbc-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="effbc-169">\<drive:>\\ \> Надстройка интеллектуального анализа данных \Users<myusername \аппдата\локал\микрософт\дата</span><span class="sxs-lookup"><span data-stu-id="effbc-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="effbc-170">Подключение к внешним источникам данных</span><span class="sxs-lookup"><span data-stu-id="effbc-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="effbc-171">В то время как средства на ленте « **анализ** » работают исключительно с данными в Excel, средства на ленте **интеллектуального анализа данных** позволяют подключаться непосредственно к внешним источникам данных для использования в качестве входных для модели или для выборки.</span><span class="sxs-lookup"><span data-stu-id="effbc-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="effbc-172">Следующие средства в этих надстройках поддерживают использование внешних данных для интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="effbc-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="effbc-173">Примеры &#40;данных SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="effbc-174">Мастер классификации &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="effbc-175">Мастер оценки &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="effbc-176">Мастер кластеров &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="effbc-177">Мастер прогнозов &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="effbc-178">Создание структуры интеллектуального анализа &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="effbc-179">Диаграмма точности &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="effbc-180">Диаграмма роста прибыли &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="effbc-181">Матрица классификации &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="effbc-182">Использование служб Analysis Services в качестве источника данных</span><span class="sxs-lookup"><span data-stu-id="effbc-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="effbc-183">Нельзя напрямую получать доступ к данным, сохраненным в кубе или в табличной модели [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="effbc-184">Вместо этого создайте соединение в Excel с сервером [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и используйте данные для создания модели.</span><span class="sxs-lookup"><span data-stu-id="effbc-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="effbc-185">Реляционные источники данных</span><span class="sxs-lookup"><span data-stu-id="effbc-185">Relational Data Sources</span></span>  
 <span data-ttu-id="effbc-186">Если нужно использовать данные из реляционного источника в качестве вводных данных для модели, можно подключиться к следующим версиям SQL Server:</span><span class="sxs-lookup"><span data-stu-id="effbc-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="effbc-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="effbc-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="effbc-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="effbc-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="effbc-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="effbc-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="effbc-190">Также можно получить данные из любого реляционного источника данных, которые поддерживается в качестве источника данных в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="effbc-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="effbc-191">Дополнительные сведения о поддерживаемых источниках данных см. [в разделе источники данных в многомерных моделях](multidimensional-models/data-sources-in-multidimensional-models.md) .</span><span class="sxs-lookup"><span data-stu-id="effbc-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="effbc-192">Обратите внимание, что следующие типы данных нельзя использовать для интеллектуального анализа данных. При включении этих данных в процесс создания модели возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="effbc-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="effbc-193">ntext</span><span class="sxs-lookup"><span data-stu-id="effbc-193">ntext</span></span>  
  
-   <span data-ttu-id="effbc-194">binary</span><span class="sxs-lookup"><span data-stu-id="effbc-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="effbc-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="effbc-195">See Also</span></span>  
 [<span data-ttu-id="effbc-196">Трассировка &#40;клиента интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="effbc-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
