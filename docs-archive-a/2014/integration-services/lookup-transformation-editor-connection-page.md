---
title: Редактор преобразования "Уточняющий запрос" (страница "соединение") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664322"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="25ef7-102">Редактор преобразования «Уточняющий запрос» (страница «Соединение»)</span><span class="sxs-lookup"><span data-stu-id="25ef7-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="25ef7-103">Используйте страницу **Соединение** диалогового окна **Редактор преобразования «Уточняющий запрос»** для выбора диспетчера соединения.</span><span class="sxs-lookup"><span data-stu-id="25ef7-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="25ef7-104">При выборе диспетчера соединений OLE DB также выбирается и запрос, таблица или представление для формирования эталонного набора данных.</span><span class="sxs-lookup"><span data-stu-id="25ef7-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="25ef7-105">Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="25ef7-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="25ef7-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="25ef7-106">Options</span></span>  
 <span data-ttu-id="25ef7-107">При выборе пунктов **Полное кэширование** и **Диспетчер соединений с кэшем** на странице «Общие» диалогового окна **Редактор преобразования «Уточняющий запрос»** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="25ef7-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="25ef7-108">**Диспетчер соединений с кэшем**</span><span class="sxs-lookup"><span data-stu-id="25ef7-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="25ef7-109">Выберите из списка существующий диспетчер соединений с кэшем или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="25ef7-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="25ef7-110">**Создать**</span><span class="sxs-lookup"><span data-stu-id="25ef7-110">**New**</span></span>  
 <span data-ttu-id="25ef7-111">Создайте новое соединение с помощью диалогового окна **Редактор диспетчера соединений с кэшем** .</span><span class="sxs-lookup"><span data-stu-id="25ef7-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="25ef7-112">При выборе пунктов **Полное кэширование**, **Частичное кэширование**или **Без кэширования**, а также **Диспетчер соединений OLE DB**на странице «Общие» диалогового окна **Редактор преобразования «Уточняющий запрос»** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="25ef7-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="25ef7-113">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="25ef7-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="25ef7-114">Выберите существующий диспетчер соединений OLE DB из списка или создайте новое подключение, выбрав пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="25ef7-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="25ef7-115">**Создать**</span><span class="sxs-lookup"><span data-stu-id="25ef7-115">**New**</span></span>  
 <span data-ttu-id="25ef7-116">Создайте новое соединение с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="25ef7-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="25ef7-117">**Использовать таблицу или представление**</span><span class="sxs-lookup"><span data-stu-id="25ef7-117">**Use a table or view**</span></span>  
 <span data-ttu-id="25ef7-118">Выберите существующую таблицу или представление из списка или создайте новую таблицу, нажав кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="25ef7-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25ef7-119">Если на странице **Дополнительно\*\*\*\*Редактора преобразования «Уточняющий запрос»** задать инструкцию SQL, то эта инструкция принудительно переопределит имя таблицы, выбранное там.</span><span class="sxs-lookup"><span data-stu-id="25ef7-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="25ef7-120">Дополнительные сведения см. в разделе [Редактор преобразования "Уточняющий запрос" (страница "Дополнительно")](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="25ef7-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="25ef7-121">**Создать**</span><span class="sxs-lookup"><span data-stu-id="25ef7-121">**New**</span></span>  
 <span data-ttu-id="25ef7-122">Создайте новую таблицу с помощью диалогового окна **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="25ef7-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="25ef7-123">**Использовать результаты SQL-запроса**</span><span class="sxs-lookup"><span data-stu-id="25ef7-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="25ef7-124">Выберите этот параметр для поиска существующего запроса, создания нового запроса, проверки синтаксиса запроса и просмотра результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="25ef7-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="25ef7-125">**Создать запрос**</span><span class="sxs-lookup"><span data-stu-id="25ef7-125">**Build query**</span></span>  
 <span data-ttu-id="25ef7-126">Создайте для выполнения инструкцию Transact-SQL с помощью **Построителя запросов**, графического средства, используемого для создания запросов с помощью просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="25ef7-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="25ef7-127">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="25ef7-127">**Browse**</span></span>  
 <span data-ttu-id="25ef7-128">Используйте этот параметр для просмотра ранее созданного запроса, сохраненного в файле.</span><span class="sxs-lookup"><span data-stu-id="25ef7-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="25ef7-129">**Анализ запроса**</span><span class="sxs-lookup"><span data-stu-id="25ef7-129">**Parse Query**</span></span>  
 <span data-ttu-id="25ef7-130">Проверка синтаксиса запроса.</span><span class="sxs-lookup"><span data-stu-id="25ef7-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="25ef7-131">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="25ef7-131">**Preview**</span></span>  
 <span data-ttu-id="25ef7-132">Просмотрите предварительные результаты, используя диалоговое окно **Предварительный просмотр результатов запроса** .</span><span class="sxs-lookup"><span data-stu-id="25ef7-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="25ef7-133">В окне предварительного просмотра может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="25ef7-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="25ef7-134">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="25ef7-134">External Resources</span></span>  
 <span data-ttu-id="25ef7-135">Запись в блоге [Режимы кэша уточняющих запросов](https://go.microsoft.com/fwlink/?LinkId=219518) на сайте blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="25ef7-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ef7-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="25ef7-136">See Also</span></span>  
 <span data-ttu-id="25ef7-137">[Редактор преобразования "Уточняющий запрос" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="25ef7-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="25ef7-138">[Редактор преобразования «Уточняющий запрос» &#40;столбцов&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="25ef7-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="25ef7-139">[Редактор преобразования "Уточняющий запрос" &#40;страница "Дополнительно"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="25ef7-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="25ef7-140">[Редактор преобразования "Уточняющий запрос" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="25ef7-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="25ef7-141">преобразование «Нечеткий уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="25ef7-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
