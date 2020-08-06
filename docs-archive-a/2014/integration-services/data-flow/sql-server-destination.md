---
title: Назначение SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729673"
---
# <a name="sql-server-destination"></a><span data-ttu-id="28505-102">назначение «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="28505-102">SQL Server Destination</span></span>
  <span data-ttu-id="28505-103">Назначение «SQL Server» подключается к локальной базе данных служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и производит массовую загрузку данных в таблицы и представления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28505-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="28505-104">Нельзя использовать назначение «SQL Server» в пакетах, получающих доступ к базе данных служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="28505-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="28505-105">Вместо этого пакеты должны использовать назначение «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="28505-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="28505-106">Дополнительные сведения см. в разделе [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="28505-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="28505-107">Разрешения</span><span class="sxs-lookup"><span data-stu-id="28505-107">Permissions</span></span>  
 <span data-ttu-id="28505-108">Пользователям, выполняющим пакеты, которые содержат назначение «SQL Server», необходимо разрешение на «Создание глобальных объектов».</span><span class="sxs-lookup"><span data-stu-id="28505-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="28505-109">Предоставить это разрешение пользователям можно с помощью средства политики локальной безопасности, доступного в меню **Администрирование** .</span><span class="sxs-lookup"><span data-stu-id="28505-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="28505-110">Если при выполнении пакета, который использует назначение «SQL Server», получено сообщение об ошибке, убедитесь, что учетная запись, под которой был запущен пакет, имеет разрешение на «Создание глобальных объектов».</span><span class="sxs-lookup"><span data-stu-id="28505-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="28505-111">Массовые вставки</span><span class="sxs-lookup"><span data-stu-id="28505-111">Bulk Inserts</span></span>  
 <span data-ttu-id="28505-112">При попытке использовать назначение «SQL Server» для массовой загрузки данных в удаленную базу данных SQL Server может появиться сообщение об ошибке, которое будет иметь следующий вид: «Доступна запись OLE DB».</span><span class="sxs-lookup"><span data-stu-id="28505-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="28505-113">Источник: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Описание: "Не удалось выполнить массовую загрузку, поскольку невозможно открыть объект сопоставления файлов служб "Global\DTSQLIMPORT".</span><span class="sxs-lookup"><span data-stu-id="28505-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="28505-114">Код ошибки операционной системы 2 (система не может найти указанный файл).</span><span class="sxs-lookup"><span data-stu-id="28505-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="28505-115">Убедитесь, что доступ к локальному серверу осуществляется через систему безопасности Windows"».</span><span class="sxs-lookup"><span data-stu-id="28505-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="28505-116">Назначение "SQL Server" предлагает такую же высокоскоростную вставку данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , что и задача "Массовая вставка". Однако используя назначение "SQL Server", пакет может применить преобразования к столбцу раньше, чем данные будут загружены в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28505-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="28505-117">Для загрузки данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]необходимо рассмотреть возможность использования назначения «SQL Server» вместо назначения «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="28505-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="28505-118">Параметры массовой вставки</span><span class="sxs-lookup"><span data-stu-id="28505-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="28505-119">Если назначение «SQL Server» использует режим доступа быстрой загрузки данных, можно задать следующие параметры быстрой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="28505-120">Хранить значения идентификаторов из файла импортируемых данных или использовать уникальные значения, назначенные [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28505-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="28505-121">Хранить в памяти значения NULL во время операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="28505-122">Проверить ограничения целевых таблиц или представлений во время операции массового импорта.</span><span class="sxs-lookup"><span data-stu-id="28505-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="28505-123">Получить блокировку на уровне таблиц на период операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="28505-124">Выполнить триггеры Insert, определенные в целевой таблице во время операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="28505-125">Указать номер первой строки во входе для загрузки во время операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="28505-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="28505-126">Указать номер последней строки во входе для загрузки во время операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="28505-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="28505-127">Указать максимально допустимое число ошибок, при достижении которого операция массовой загрузки отменяется.</span><span class="sxs-lookup"><span data-stu-id="28505-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="28505-128">Каждая строка, которая не может быть импортирована, считается как одна ошибка.</span><span class="sxs-lookup"><span data-stu-id="28505-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="28505-129">Указать столбцы во входе, которые содержат отсортированные данные.</span><span class="sxs-lookup"><span data-stu-id="28505-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="28505-130">Дополнительные сведения о параметрах массовой загрузки см. в разделе [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28505-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="28505-131">Повышение производительности</span><span class="sxs-lookup"><span data-stu-id="28505-131">Performance Improvements</span></span>  
 <span data-ttu-id="28505-132">Чтобы повысить производительность массовой вставки и доступа к таблице данных во время операции массовой вставки, необходимо изменить параметры по умолчанию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28505-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="28505-133">Не проверять ограничения целевых таблиц или представлений во время операции массового импорта.</span><span class="sxs-lookup"><span data-stu-id="28505-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="28505-134">Не выполнять триггеры Insert, определенные в целевой таблице во время операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="28505-135">Не применять блокировку таблицы.</span><span class="sxs-lookup"><span data-stu-id="28505-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="28505-136">Таким образом, таблица остается доступной для других пользователей и приложений во время операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="28505-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="28505-137">Настройка назначения SQL Server</span><span class="sxs-lookup"><span data-stu-id="28505-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="28505-138">Назначение «SQL Server» можно настроить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="28505-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="28505-139">Укажите таблицу или представление, в которые будет производиться массовая загрузка.</span><span class="sxs-lookup"><span data-stu-id="28505-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="28505-140">Настройте операцию массовой загрузки, указав такие параметры, как управление очередностью.</span><span class="sxs-lookup"><span data-stu-id="28505-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="28505-141">Укажите, можно ли произвести фиксацию всех строк в одном пакете, или установите максимальное количество строк, фиксируемых в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="28505-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="28505-142">Укажите время ожидания для операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="28505-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="28505-143">Это назначение использует диспетчер соединений OLE DB для подключения к источнику данных, и диспетчер соединений определяет используемый поставщик OLE DB.</span><span class="sxs-lookup"><span data-stu-id="28505-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="28505-144">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="28505-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="28505-145">Проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] также предоставляет объект источника данных, из которого можно создать диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="28505-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="28505-146">Это предоставляет назначению «SQL Server» доступ к источникам данных и представлениям источника данных.</span><span class="sxs-lookup"><span data-stu-id="28505-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="28505-147">Назначение «SQL Server» имеет один вход.</span><span class="sxs-lookup"><span data-stu-id="28505-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="28505-148">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="28505-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="28505-149">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="28505-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="28505-150">Дополнительные сведения о свойствах, которые могут быть заданы в диалоговом окне **Редактор назначения SQL Server** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="28505-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="28505-151">Редактор назначения SQL (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="28505-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="28505-152">Редактор назначения "SQL" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="28505-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="28505-153">Редактор назначения SQL (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="28505-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="28505-154">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="28505-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="28505-155">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="28505-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="28505-156">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="28505-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="28505-157">Пользовательские свойства назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="28505-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="28505-158">Дополнительные сведения о настройке свойств см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="28505-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="28505-159">Выполнение массовой загрузки данных с помощью назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="28505-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="28505-160">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="28505-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="28505-161">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="28505-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="28505-162">Выполнение массовой загрузки данных с помощью назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="28505-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="28505-163">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="28505-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="28505-164">См. также</span><span class="sxs-lookup"><span data-stu-id="28505-164">Related Content</span></span>  
  
-   <span data-ttu-id="28505-165">Техническая статья [В системах, поддерживающих контроль учетных записей, может быть получена ошибка «Не удалось подготовить массовую вставку данных служб SSIS»](https://go.microsoft.com/fwlink/?LinkId=199482)на сайте support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="28505-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="28505-166">Техническая статья [Руководство по производительности загрузки данных](https://go.microsoft.com/fwlink/?LinkId=233700)на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="28505-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="28505-167">Техническая статья [Использование служб SQL Server Integration Services для массовой загрузки данных](https://go.microsoft.com/fwlink/?LinkId=233701)размещена на сайте simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="28505-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28505-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="28505-168">See Also</span></span>  
 [<span data-ttu-id="28505-169">Поток данных</span><span class="sxs-lookup"><span data-stu-id="28505-169">Data Flow</span></span>](data-flow.md)  
  
  
