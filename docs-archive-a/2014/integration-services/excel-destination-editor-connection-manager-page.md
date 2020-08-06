---
title: Редактор назначения «Excel» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665030"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="2fb9b-102">Редактор назначения «Excel» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="2fb9b-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="2fb9b-103">Используйте страницу **Диспетчер соединений** в диалоговом окне **Редактор назначения «Excel»** , чтобы задать сведения об источнике данных и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="2fb9b-104">Назначение «Excel» загружает данные в лист или именованный диапазон в книге [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2fb9b-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fb9b-105">`CommandTimeout`Свойство назначения «Excel» недоступно в **редакторе назначения «Excel**», но может быть задано с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="2fb9b-106">Кроме того, некоторые параметры быстрой загрузки доступны только в **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="2fb9b-107">Дополнительные сведения об этих свойствах см. в подразделе «Назначение "Excel"» раздела [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2fb9b-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="2fb9b-108">Дополнительные сведения о назначении Excel см. в разделе [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2fb9b-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2fb9b-109">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="2fb9b-109">Static Options</span></span>  
 <span data-ttu-id="2fb9b-110">**Диспетчер соединений с Excel**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="2fb9b-111">Выберите из списка существующий диспетчер подключений к Excel или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="2fb9b-112">**Создать**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-112">**New**</span></span>  
 <span data-ttu-id="2fb9b-113">Создайте новый диспетчер подключений с помощью диалогового окна **Диспетчер подключений Excel** .</span><span class="sxs-lookup"><span data-stu-id="2fb9b-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="2fb9b-114">**Режим доступа к данным**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-114">**Data access mode**</span></span>  
 <span data-ttu-id="2fb9b-115">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="2fb9b-116">Параметр</span><span class="sxs-lookup"><span data-stu-id="2fb9b-116">Option</span></span>|<span data-ttu-id="2fb9b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2fb9b-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2fb9b-118">Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="2fb9b-118">Table or view</span></span>|<span data-ttu-id="2fb9b-119">Загружает данные в лист или именованный диапазон источника данных Excel.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="2fb9b-120">Переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="2fb9b-120">Table name or view name variable</span></span>|<span data-ttu-id="2fb9b-121">Укажите переменную, содержащую имя листа или диапазона.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="2fb9b-122">**Дополнительные сведения** [Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="2fb9b-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="2fb9b-123">Команда SQL</span><span class="sxs-lookup"><span data-stu-id="2fb9b-123">SQL command</span></span>|<span data-ttu-id="2fb9b-124">Загрузка данных в назначение «Excel» с помощью SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="2fb9b-125">**Имя листа Excel**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="2fb9b-126">Выберите назначение Excel из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="2fb9b-127">Если этот список пустой, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="2fb9b-128">**Создать**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-128">**New**</span></span>  
 <span data-ttu-id="2fb9b-129">Выберите **Создать** для открытия диалогового окна **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="2fb9b-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="2fb9b-130">После нажатия кнопки **OK**создается файл Excel, на который указывает **Диспетчер соединений с Excel** .</span><span class="sxs-lookup"><span data-stu-id="2fb9b-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="2fb9b-131">**Просмотр существующих данных**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-131">**View Existing Data**</span></span>  
 <span data-ttu-id="2fb9b-132">Просмотрите предварительные результаты, используя диалоговое окно **Предварительный просмотр результатов запроса** .</span><span class="sxs-lookup"><span data-stu-id="2fb9b-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="2fb9b-133">В окне «Предварительный просмотр» может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2fb9b-134"> Если выделенный **Диспетчер соединений с Excel** указывает на несуществующий файл Excel, то при нажатии на эту кнопку появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="2fb9b-135">Динамические параметры режима доступа к данным</span><span class="sxs-lookup"><span data-stu-id="2fb9b-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="2fb9b-136">Режим доступа к данным = Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="2fb9b-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="2fb9b-137">**Имя листа Excel**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="2fb9b-138">Выберите имя листа или именованного диапазона из списка доступных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="2fb9b-139">Режим доступа к данным — переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="2fb9b-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="2fb9b-140">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-140">**Variable name**</span></span>  
 <span data-ttu-id="2fb9b-141">Укажите переменную, содержащую имя листа или именованного диапазона.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="2fb9b-142">Режим доступа к данным — команда SQL</span><span class="sxs-lookup"><span data-stu-id="2fb9b-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="2fb9b-143">**Текст команды SQL**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-143">**SQL command text**</span></span>  
 <span data-ttu-id="2fb9b-144">Введите текст SQL-запроса, создайте запрос, нажав кнопку **Создать запрос**, или выберите файл, содержащий текст запроса, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="2fb9b-145">**Создать запрос**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-145">**Build Query**</span></span>  
 <span data-ttu-id="2fb9b-146">Воспользуйтесь диалоговым окном **Построитель запросов** для визуального конструирования SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="2fb9b-147">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-147">**Browse**</span></span>  
 <span data-ttu-id="2fb9b-148">Воспользуйтесь диалоговым окном **Открыть** для выбора файла, содержащего текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="2fb9b-149">**Анализ запроса**</span><span class="sxs-lookup"><span data-stu-id="2fb9b-149">**Parse Query**</span></span>  
 <span data-ttu-id="2fb9b-150">Проверить синтаксис текста запроса.</span><span class="sxs-lookup"><span data-stu-id="2fb9b-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb9b-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="2fb9b-151">See Also</span></span>  
 <span data-ttu-id="2fb9b-152">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2fb9b-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2fb9b-153">[Редактор назначения "Excel" &#40;страниц сопоставления&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="2fb9b-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="2fb9b-154">[Редактор назначения "Excel" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="2fb9b-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="2fb9b-155">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="2fb9b-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
