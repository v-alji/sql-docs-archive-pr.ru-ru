---
title: Редактор назначения ODBC (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734365"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="17425-102">Редактор назначения «ODBC» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="17425-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="17425-103">Страница **Диспетчер соединений** диалогового окна **Редактор назначения ODBC** используется для выбора диспетчера соединений ODBC для назначения.</span><span class="sxs-lookup"><span data-stu-id="17425-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="17425-104">На этой странице также можно выбрать таблицу или представление базы данных</span><span class="sxs-lookup"><span data-stu-id="17425-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="17425-105">Дополнительные сведения о назначении ODBC см. в разделе [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="17425-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="17425-106">**Открытие страницы диспетчера соединений в редакторе назначения ODBC**</span><span class="sxs-lookup"><span data-stu-id="17425-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="17425-107">Список задач</span><span class="sxs-lookup"><span data-stu-id="17425-107">Task List</span></span>  
  
-   <span data-ttu-id="17425-108">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="17425-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="17425-109">На вкладке **Поток данных** дважды щелкните назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="17425-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="17425-110">В окне **Редактор назначения ODBC**нажмите кнопку **Диспетчер соединений**.</span><span class="sxs-lookup"><span data-stu-id="17425-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="17425-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="17425-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="17425-112">Диспетчер соединений</span><span class="sxs-lookup"><span data-stu-id="17425-112">Connection manager</span></span>  
 <span data-ttu-id="17425-113">Выберите из списка существующий диспетчер соединений ODBC или нажмите кнопку «Создать», чтобы создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="17425-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="17425-114">Соединение может устанавливаться с любой базой данных, поддерживающей ODBC.</span><span class="sxs-lookup"><span data-stu-id="17425-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="17425-115">Создать</span><span class="sxs-lookup"><span data-stu-id="17425-115">New</span></span>  
 <span data-ttu-id="17425-116">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="17425-116">Click **New**.</span></span> <span data-ttu-id="17425-117">Откроется диалоговое окно **Настройка редактора диспетчера соединений ODBC** , где можно создать новый диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="17425-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="17425-118">Режим доступа к данным</span><span class="sxs-lookup"><span data-stu-id="17425-118">Data Access Mode</span></span>  
 <span data-ttu-id="17425-119">Выберите метод загрузки данных в назначение.</span><span class="sxs-lookup"><span data-stu-id="17425-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="17425-120">Доступные параметры показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="17425-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="17425-121">Параметр</span><span class="sxs-lookup"><span data-stu-id="17425-121">Option</span></span>|<span data-ttu-id="17425-122">Description</span><span class="sxs-lookup"><span data-stu-id="17425-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="17425-123">Имя таблицы — пакетом</span><span class="sxs-lookup"><span data-stu-id="17425-123">Table Name - Batch</span></span>|<span data-ttu-id="17425-124">Выберите этот параметр, чтобы настроить назначение ODBC для работы в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="17425-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="17425-125">Если выбран этот параметр, становятся доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="17425-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="17425-126">**Имя таблицы или представления**: выберите доступную таблицу или представление из списка.</span><span class="sxs-lookup"><span data-stu-id="17425-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="17425-127">Этот список содержит только первые 1000 таблиц.</span><span class="sxs-lookup"><span data-stu-id="17425-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="17425-128">Если база данных содержит больше 1000 таблиц, можно ввести начальную часть имени таблицы или воспользоваться подстановочным знаком (\*), чтобы ввести любую часть имени для вывода нужных таблиц.</span><span class="sxs-lookup"><span data-stu-id="17425-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="17425-129">**Размер пакета**: введите размер пакета для массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="17425-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="17425-130">Это количество строк, загружаемых в виде одного пакета.</span><span class="sxs-lookup"><span data-stu-id="17425-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="17425-131">Имя таблицы — построчно</span><span class="sxs-lookup"><span data-stu-id="17425-131">Table Name - Row by Row</span></span>|<span data-ttu-id="17425-132">Выберите этот параметр, чтобы настроить назначение ODBC для вставки каждой строки в целевую таблицу по отдельности.</span><span class="sxs-lookup"><span data-stu-id="17425-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="17425-133">Если выбран этот параметр, становится доступен следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="17425-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="17425-134">**Имя таблицы или представления**: выберите доступную таблицу или представление базы данных из списка.</span><span class="sxs-lookup"><span data-stu-id="17425-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="17425-135">Этот список содержит только первые 1000 таблиц.</span><span class="sxs-lookup"><span data-stu-id="17425-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="17425-136">Если база данных содержит больше 1000 таблиц, можно ввести начальную часть имени таблицы или воспользоваться символом-шаблоном (\*), чтобы ввести любую часть имени для вывода нужных таблиц.</span><span class="sxs-lookup"><span data-stu-id="17425-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="17425-137">Preview (Предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="17425-137">Preview</span></span>  
 <span data-ttu-id="17425-138">Нажмите кнопку **Просмотр** , чтобы просмотреть первые строки (до 200) данных для выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="17425-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17425-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="17425-139">See Also</span></span>  
 <span data-ttu-id="17425-140">[Пользовательские свойства назначения «ODBC»](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="17425-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="17425-141">[Редактор назначения ODBC &#40;страниц сопоставления&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="17425-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="17425-142">Редактор назначения ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="17425-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
