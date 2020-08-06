---
title: Редактор источника «Excel» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665014"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="f8b1c-102">Редактор источника Excel (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="f8b1c-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="f8b1c-103">Используйте раздел **Диспетчер соединений** диалогового окна **Редактор источника «Excel»** , чтобы выбрать используемую рабочую книгу [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8b1c-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="f8b1c-104">Источник Excel считывает данные из рабочего листа или из именованного диапазона в существующей рабочей книге.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8b1c-105">`CommandTimeout`Свойство источника Excel недоступно в **редакторе источника Excel**, но может быть задано с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="f8b1c-106">Дополнительные сведения о данном свойстве см. в подразделе «Источник Excel» раздела [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f8b1c-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="f8b1c-107">Дополнительные сведения об источнике Excel см. в разделе [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="f8b1c-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="f8b1c-108">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="f8b1c-108">Static Options</span></span>  
 <span data-ttu-id="f8b1c-109">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="f8b1c-110">Выберите из списка существующий диспетчер подключений к Excel или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="f8b1c-111">**Создать**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-111">**New**</span></span>  
 <span data-ttu-id="f8b1c-112">Создайте новый диспетчер подключений с помощью диалогового окна **Диспетчер подключений Excel** .</span><span class="sxs-lookup"><span data-stu-id="f8b1c-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="f8b1c-113">**Режим доступа к данным**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-113">**Data access mode**</span></span>  
 <span data-ttu-id="f8b1c-114">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="f8b1c-115">Значение</span><span class="sxs-lookup"><span data-stu-id="f8b1c-115">Value</span></span>|<span data-ttu-id="f8b1c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f8b1c-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8b1c-117">Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="f8b1c-117">Table or view</span></span>|<span data-ttu-id="f8b1c-118">Получение данных из электронной таблицы или именованного диапазона файла Excel.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="f8b1c-119">Переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="f8b1c-119">Table name or view name variable</span></span>|<span data-ttu-id="f8b1c-120">Укажите переменную, содержащую имя листа или диапазона.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="f8b1c-121">**Дополнительные сведения.** [Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="f8b1c-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="f8b1c-122">Команда SQL</span><span class="sxs-lookup"><span data-stu-id="f8b1c-122">SQL command</span></span>|<span data-ttu-id="f8b1c-123">Получение данных из файла Excel с использованием SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="f8b1c-124">Дополнительные сведения о синтаксисе запросов см. в разделе [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="f8b1c-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="f8b1c-125">Команда SQL из переменной</span><span class="sxs-lookup"><span data-stu-id="f8b1c-125">SQL command from variable</span></span>|<span data-ttu-id="f8b1c-126">Задайте текст SQL-запроса в переменную.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="f8b1c-127">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-127">**Preview**</span></span>  
 <span data-ttu-id="f8b1c-128">Осуществляйте предварительный просмотр результатов в диалоговом окне **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="f8b1c-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="f8b1c-129">В окне «Предварительный просмотр» может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="f8b1c-130">Динамические параметры режима доступа к данным</span><span class="sxs-lookup"><span data-stu-id="f8b1c-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="f8b1c-131">Режим доступа к данным = Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="f8b1c-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="f8b1c-132">**Имя листа Excel**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="f8b1c-133">Выберите в книге Excel из списка имя листа или именованного диапазона.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="f8b1c-134">Режим доступа к данным — переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="f8b1c-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="f8b1c-135">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-135">**Variable name**</span></span>  
 <span data-ttu-id="f8b1c-136">Укажите переменную, содержащую имя листа или именованного диапазона.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="f8b1c-137">Режим доступа к данным — команда SQL</span><span class="sxs-lookup"><span data-stu-id="f8b1c-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="f8b1c-138">**Текст команды SQL**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-138">**SQL command text**</span></span>  
 <span data-ttu-id="f8b1c-139">Введите текст SQL-запроса, создайте запрос, нажав кнопку **Создать запрос**, или выберите файл, содержащий текст запроса, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="f8b1c-140">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-140">**Parameters**</span></span>  
 <span data-ttu-id="f8b1c-141">Если введен параметризованный запрос, где в тексте запроса в качестве заполнителя параметра использовался знак ?,</span><span class="sxs-lookup"><span data-stu-id="f8b1c-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="f8b1c-142">воспользуйтесь диалоговым окном **Установка параметров запроса** для сопоставления входных параметров запроса и переменных пакета.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="f8b1c-143">**Создать запрос**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-143">**Build query**</span></span>  
 <span data-ttu-id="f8b1c-144">Воспользуйтесь диалоговым окном **Построитель запросов** для визуального конструирования SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="f8b1c-145">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-145">**Browse**</span></span>  
 <span data-ttu-id="f8b1c-146">Воспользуйтесь диалоговым окном **Открыть** для выбора файла, содержащего текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="f8b1c-147">**Анализ запроса**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-147">**Parse query**</span></span>  
 <span data-ttu-id="f8b1c-148">Проверить синтаксис текста запроса.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="f8b1c-149">Режим доступа к данным = Команда SQL из переменной</span><span class="sxs-lookup"><span data-stu-id="f8b1c-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="f8b1c-150">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="f8b1c-150">**Variable name**</span></span>  
 <span data-ttu-id="f8b1c-151">Выберите переменную, содержащую текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="f8b1c-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b1c-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8b1c-152">See Also</span></span>  
 <span data-ttu-id="f8b1c-153">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f8b1c-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f8b1c-154">[Редактор источника "Excel" &#40;столбцы "&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="f8b1c-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="f8b1c-155">[Редактор источника "Excel" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f8b1c-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="f8b1c-156">[Диспетчер соединений с Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f8b1c-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="f8b1c-157">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="f8b1c-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
