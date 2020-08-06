---
title: Редактор источника «ADO NET» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736683"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="ff6ca-102">Редактор источника данных «ADO.NET» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="ff6ca-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="ff6ca-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор назначения «ADO.NET»** для выбора соединения [!INCLUDE[vstecado](../includes/vstecado-md.md)] применительно к источнику.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="ff6ca-104">На этой странице также можно выбрать таблицу или представление базы данных.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="ff6ca-105">Дополнительные сведения об источниках данных «ADO.NET» см. в разделе [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="ff6ca-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="ff6ca-106">**Открытие страницы «Диспетчер соединений»**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="ff6ca-107">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий источник данных «ADO.NET».</span><span class="sxs-lookup"><span data-stu-id="ff6ca-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="ff6ca-108">На вкладке **Поток данных** дважды щелкните источник данных "ADO.NET".</span><span class="sxs-lookup"><span data-stu-id="ff6ca-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="ff6ca-109">В окне **Редактор источника «ADO.NET»** нажмите кнопку **Диспетчер соединений**.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="ff6ca-110">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="ff6ca-110">Static Options</span></span>  
 <span data-ttu-id="ff6ca-111">**Диспетчер соединений ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="ff6ca-112">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="ff6ca-113">**Создать**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-113">**New**</span></span>  
 <span data-ttu-id="ff6ca-114">Создайте новый диспетчер соединений с помощью диалогового окна **Настройка диспетчера соединений ADO.NET** .</span><span class="sxs-lookup"><span data-stu-id="ff6ca-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="ff6ca-115">**Режим доступа к данным**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-115">**Data access mode**</span></span>  
 <span data-ttu-id="ff6ca-116">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="ff6ca-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="ff6ca-117">Option</span></span>|<span data-ttu-id="ff6ca-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ff6ca-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ff6ca-119">Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="ff6ca-119">Table or view</span></span>|<span data-ttu-id="ff6ca-120">Выборка данных из таблицы или представления в источнике данных [!INCLUDE[vstecado](../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff6ca-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="ff6ca-121">Команда SQL</span><span class="sxs-lookup"><span data-stu-id="ff6ca-121">SQL command</span></span>|<span data-ttu-id="ff6ca-122">Выборка данных из источника данных [!INCLUDE[vstecado](../includes/vstecado-md.md)] с использованием SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="ff6ca-123">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-123">**Preview**</span></span>  
 <span data-ttu-id="ff6ca-124">Осуществляйте предварительный просмотр результатов в диалоговом окне **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="ff6ca-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="ff6ca-125">В окне**Предварительный просмотр** может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff6ca-126">При предварительном просмотре столбцы с определяемым пользователем типом данных CLR не содержат данных.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="ff6ca-127">Вместо этого отображаются значения \<value too big to display> или System.Byte[].</span><span class="sxs-lookup"><span data-stu-id="ff6ca-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="ff6ca-128">Первый вариант отображается во время доступа к источнику данных с помощью поставщика [!INCLUDE[vstecado](../includes/vstecado-md.md)] , а последний — при использовании поставщика данных для собственного клиента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff6ca-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="ff6ca-129">Динамические параметры режима доступа к данным</span><span class="sxs-lookup"><span data-stu-id="ff6ca-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="ff6ca-130">Режим доступа к данным = Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="ff6ca-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="ff6ca-131">**Имя таблицы или представления**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="ff6ca-132">Выберите имя таблицы или представления из списка доступных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="ff6ca-133">Режим доступа к данным — команда SQL</span><span class="sxs-lookup"><span data-stu-id="ff6ca-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="ff6ca-134">**Текст команды SQL**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-134">**SQL command text**</span></span>  
 <span data-ttu-id="ff6ca-135">Введите текст SQL-запроса, постройте запрос, нажав кнопку **Создать запрос**, или выберите файл, содержащий текст запроса, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="ff6ca-136">**Создать запрос**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-136">**Build query**</span></span>  
 <span data-ttu-id="ff6ca-137">Воспользуйтесь диалоговым окном **Построитель запросов** для визуального конструирования SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="ff6ca-138">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="ff6ca-138">**Browse**</span></span>  
 <span data-ttu-id="ff6ca-139">Воспользуйтесь диалоговым окном **Открыть** для выбора файла, содержащего текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6ca-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff6ca-140">See Also</span></span>  
 <span data-ttu-id="ff6ca-141">[Редактор источника «ADO NET» &#40;столбцы&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ff6ca-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="ff6ca-142">[Редактор источника ADO NET &#40;страница вывода ошибок&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="ff6ca-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="ff6ca-143">Диспетчер подключений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff6ca-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
