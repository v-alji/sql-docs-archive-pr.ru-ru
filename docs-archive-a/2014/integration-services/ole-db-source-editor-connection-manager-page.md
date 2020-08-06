---
title: Редактор источника OLE DB (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667811"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="fcc02-102">Редактор источника OLE DB (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="fcc02-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="fcc02-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор источника OLE DB** для выбора диспетчера соединений OLE DB для источника.</span><span class="sxs-lookup"><span data-stu-id="fcc02-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="fcc02-104">На этой странице также можно выбрать таблицу или представление базы данных.</span><span class="sxs-lookup"><span data-stu-id="fcc02-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc02-105">Чтобы загрузить данные из источника данных, использующего [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, используйте источник OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fcc02-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="fcc02-106">Нельзя использовать источник Excel для загрузки данных из источника данных Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="fcc02-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="fcc02-107">Дополнительные сведения см. в разделе [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fcc02-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="fcc02-108">Чтобы загрузить данные из источника данных, использующего [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 или более раннюю версию, используйте источник Excel.</span><span class="sxs-lookup"><span data-stu-id="fcc02-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="fcc02-109">Дополнительные сведения см. в разделе [Редактор источника Excel (страница "Диспетчер соединений")](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="fcc02-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc02-110">`CommandTimeout`Свойство источника OLE DB недоступно в **редакторе источника OLE DB**, но может быть задано с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="fcc02-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="fcc02-111">Дополнительные сведения о данном свойстве см. в подразделе «Источник Excel» раздела [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fcc02-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="fcc02-112">Дополнительные сведения об источнике OLE DB см. в разделе [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="fcc02-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="fcc02-113">Откройте редактор источника OLE DB (страницу диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="fcc02-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="fcc02-114">Добавьте источник OLE DB к пакету служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc02-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="fcc02-115">Щелкните правой кнопкой мыши компонент источника, а затем выберите пункт **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="fcc02-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="fcc02-116">Щелкните **Диспетчер соединений**.</span><span class="sxs-lookup"><span data-stu-id="fcc02-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="fcc02-117">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="fcc02-117">Static Options</span></span>  
 <span data-ttu-id="fcc02-118">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="fcc02-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="fcc02-119">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fcc02-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="fcc02-120">**Создать**</span><span class="sxs-lookup"><span data-stu-id="fcc02-120">**New**</span></span>  
 <span data-ttu-id="fcc02-121">Создайте новый диспетчер соединений с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="fcc02-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="fcc02-122">**Режим доступа к данным**</span><span class="sxs-lookup"><span data-stu-id="fcc02-122">**Data access mode**</span></span>  
 <span data-ttu-id="fcc02-123">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="fcc02-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="fcc02-124">Параметр</span><span class="sxs-lookup"><span data-stu-id="fcc02-124">Option</span></span>|<span data-ttu-id="fcc02-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fcc02-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fcc02-126">Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="fcc02-126">Table or view</span></span>|<span data-ttu-id="fcc02-127">Получение данных из таблицы или представления в источнике данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fcc02-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="fcc02-128">Переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="fcc02-128">Table name or view name variable</span></span>|<span data-ttu-id="fcc02-129">Задайте переменную, содержащую имя таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="fcc02-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="fcc02-130">**Дополнительные сведения.** [Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="fcc02-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="fcc02-131">Команда SQL</span><span class="sxs-lookup"><span data-stu-id="fcc02-131">SQL command</span></span>|<span data-ttu-id="fcc02-132">Получение данных из источника данных OLE DB с использованием SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc02-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="fcc02-133">Команда SQL из переменной</span><span class="sxs-lookup"><span data-stu-id="fcc02-133">SQL command from variable</span></span>|<span data-ttu-id="fcc02-134">Задайте текст SQL-запроса в переменную.</span><span class="sxs-lookup"><span data-stu-id="fcc02-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="fcc02-135">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="fcc02-135">**Preview**</span></span>  
 <span data-ttu-id="fcc02-136">Осуществляйте предварительный просмотр результатов в диалоговом окне **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="fcc02-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="fcc02-137">В окне**Предварительный просмотр** может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="fcc02-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc02-138">При предварительном просмотре столбцы с определяемым пользователем типом данных CLR не содержат данных.</span><span class="sxs-lookup"><span data-stu-id="fcc02-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="fcc02-139">Вместо этого отображаются значения \<value too big to display> или System.Byte[].</span><span class="sxs-lookup"><span data-stu-id="fcc02-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="fcc02-140">Первое отображается при доступе к источнику данных с помощью поставщика SQL OLE DB, второе — с помощью поставщика собственного клиента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcc02-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="fcc02-141">Динамические параметры режима доступа к данным</span><span class="sxs-lookup"><span data-stu-id="fcc02-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="fcc02-142">Режим доступа к данным = Таблица или представление</span><span class="sxs-lookup"><span data-stu-id="fcc02-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="fcc02-143">**Имя таблицы или представления**</span><span class="sxs-lookup"><span data-stu-id="fcc02-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="fcc02-144">Выберите имя таблицы или представления из списка доступных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="fcc02-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="fcc02-145">Режим доступа к данным — переменная, содержащая имя таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="fcc02-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="fcc02-146">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="fcc02-146">**Variable name**</span></span>  
 <span data-ttu-id="fcc02-147">Выберите переменную, содержащую имя таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="fcc02-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="fcc02-148">Режим доступа к данным — команда SQL</span><span class="sxs-lookup"><span data-stu-id="fcc02-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="fcc02-149">**Текст команды SQL**</span><span class="sxs-lookup"><span data-stu-id="fcc02-149">**SQL command text**</span></span>  
 <span data-ttu-id="fcc02-150">Введите текст SQL-запроса, постройте запрос, нажав кнопку **Создать запрос**, или выберите файл, содержащий текст запроса, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="fcc02-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="fcc02-151">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="fcc02-151">**Parameters**</span></span>  
 <span data-ttu-id="fcc02-152">Если введен параметризованный запрос, где в тексте запроса в качестве заполнителя параметра использовался знак ?,</span><span class="sxs-lookup"><span data-stu-id="fcc02-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="fcc02-153">воспользуйтесь диалоговым окном **Установка параметров запроса** для сопоставления входных параметров запроса и переменных пакета.</span><span class="sxs-lookup"><span data-stu-id="fcc02-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="fcc02-154">**Создать запрос**</span><span class="sxs-lookup"><span data-stu-id="fcc02-154">**Build query**</span></span>  
 <span data-ttu-id="fcc02-155">Воспользуйтесь диалоговым окном **Построитель запросов** для визуального конструирования SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc02-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="fcc02-156">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="fcc02-156">**Browse**</span></span>  
 <span data-ttu-id="fcc02-157">Воспользуйтесь диалоговым окном **Открыть** для выбора файла, содержащего текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc02-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="fcc02-158">**Анализ запроса**</span><span class="sxs-lookup"><span data-stu-id="fcc02-158">**Parse query**</span></span>  
 <span data-ttu-id="fcc02-159">Проверить синтаксис текста запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc02-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="fcc02-160">Режим доступа к данным = Команда SQL из переменной</span><span class="sxs-lookup"><span data-stu-id="fcc02-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="fcc02-161">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="fcc02-161">**Variable name**</span></span>  
 <span data-ttu-id="fcc02-162">Выберите переменную, содержащую текст SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="fcc02-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc02-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcc02-163">See Also</span></span>  
 <span data-ttu-id="fcc02-164">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fcc02-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fcc02-165">[Страница "&#40;столбцов" редактора источника OLE DB&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="fcc02-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="fcc02-166">[Редактор источника OLE DB &#40;странице вывода ошибок&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="fcc02-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="fcc02-167">[Извлечение данных с помощью источника OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="fcc02-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="fcc02-168">Диспетчер соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="fcc02-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
