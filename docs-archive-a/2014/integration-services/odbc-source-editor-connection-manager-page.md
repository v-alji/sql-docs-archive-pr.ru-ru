---
title: Редактор источника «ODBC» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734353"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="ff414-102">Редактор источника «ODBC» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="ff414-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="ff414-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор источника ODBC** , чтобы выбрать диспетчер соединений ODBC для источника.</span><span class="sxs-lookup"><span data-stu-id="ff414-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="ff414-104">На этой странице также можно выбрать таблицу или представление базы данных.</span><span class="sxs-lookup"><span data-stu-id="ff414-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="ff414-105">Дополнительные сведения об источнике ODBC см. в разделе [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="ff414-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="ff414-106">Список задач</span><span class="sxs-lookup"><span data-stu-id="ff414-106">Task List</span></span>  
 <span data-ttu-id="ff414-107">**Открытие страницы диспетчера соединений в редакторе источника ODBC**</span><span class="sxs-lookup"><span data-stu-id="ff414-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="ff414-108">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff414-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="ff414-109">На вкладке **Поток данных** дважды щелкните источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff414-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff414-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff414-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="ff414-111">Диспетчер соединений</span><span class="sxs-lookup"><span data-stu-id="ff414-111">Connection manager</span></span>  
 <span data-ttu-id="ff414-112">Выберите из списка существующий диспетчер соединений ODBC или нажмите кнопку **создать** , чтобы создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="ff414-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="ff414-113">Соединение может устанавливаться с любой базой данных, поддерживающей ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff414-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="ff414-114">Создать</span><span class="sxs-lookup"><span data-stu-id="ff414-114">New</span></span>  
 <span data-ttu-id="ff414-115">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ff414-115">Click **New**.</span></span> <span data-ttu-id="ff414-116">Откроется диалоговое окно **Настройка редактора диспетчера соединений ODBC** , где можно создать новый диспетчер соединений ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff414-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="ff414-117">Режим доступа к данным</span><span class="sxs-lookup"><span data-stu-id="ff414-117">Data Access Mode</span></span>  
 <span data-ttu-id="ff414-118">Выберите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="ff414-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="ff414-119">Доступные параметры показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ff414-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="ff414-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="ff414-120">Option</span></span>|<span data-ttu-id="ff414-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ff414-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ff414-122">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="ff414-122">Table Name</span></span>|<span data-ttu-id="ff414-123">Получение данных из таблицы или представления в источнике данных ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff414-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="ff414-124">Если выбран этот параметр, выберите значение из следующего списка.</span><span class="sxs-lookup"><span data-stu-id="ff414-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="ff414-125">**Имя таблицы или представления**. Выберите доступную таблицу или представление из списка или введите регулярное выражение, определяющее таблицу.</span><span class="sxs-lookup"><span data-stu-id="ff414-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="ff414-126">Этот список содержит только первые 1000 таблиц.</span><span class="sxs-lookup"><span data-stu-id="ff414-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ff414-127">Если база данных содержит больше 1000 таблиц, можно ввести начальную часть имени таблицы или воспользоваться символом-шаблоном (\*), чтобы ввести любую часть имени для вывода нужных таблиц.</span><span class="sxs-lookup"><span data-stu-id="ff414-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="ff414-128">Команда SQL</span><span class="sxs-lookup"><span data-stu-id="ff414-128">SQL command</span></span>|<span data-ttu-id="ff414-129">Получение данных из источника данных ODBC с помощью SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="ff414-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="ff414-130">Запрос следует писать с соблюдением синтаксиса исходной базы данных, в которой будет работать запрос.</span><span class="sxs-lookup"><span data-stu-id="ff414-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="ff414-131">Если выбран этот параметр, введите запрос одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="ff414-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="ff414-132">Введите текст SQL-запроса в поле **Текст команды SQL** .</span><span class="sxs-lookup"><span data-stu-id="ff414-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="ff414-133">Нажмите кнопку **Обзор** , чтобы загрузить SQL-запрос из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="ff414-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="ff414-134">Чтобы проверить синтаксис текста запроса, нажмите кнопку **Анализ запроса** .</span><span class="sxs-lookup"><span data-stu-id="ff414-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="ff414-135">Preview (Предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="ff414-135">Preview</span></span>  
 <span data-ttu-id="ff414-136">Нажмите кнопку **Просмотр** , чтобы просмотреть первые 200 строк данных, извлеченных из выбранной таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="ff414-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff414-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff414-137">See Also</span></span>  
 <span data-ttu-id="ff414-138">[Пользовательские свойства источника «ODBC»](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ff414-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="ff414-139">[Редактор источника «ODBC» &#40;столбцы&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ff414-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="ff414-140">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="ff414-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
