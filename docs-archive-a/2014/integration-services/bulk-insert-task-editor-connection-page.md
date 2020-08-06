---
title: Редактор задачи «основная вставка» (страница «соединение») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738657"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="a2e45-102">Редактор задачи «Массовая вставка» (страница «Соединение»)</span><span class="sxs-lookup"><span data-stu-id="a2e45-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="a2e45-103">Страница **Соединение** диалогового окна **Редактор задачи «Массовая вставка»** используется для указания источника и места назначения операции массовой вставки и формата для использования.</span><span class="sxs-lookup"><span data-stu-id="a2e45-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="a2e45-104">Дополнительные сведения о работе с массовыми вставками см. в разделах [Задача "Массовая вставка"](control-flow/bulk-insert-task.md) и [Файлы форматирования для импорта или экспорта данных (SQL Server)](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a2e45-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2e45-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2e45-105">Options</span></span>  
 <span data-ttu-id="a2e45-106">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="a2e45-106">**Connection**</span></span>  
 <span data-ttu-id="a2e45-107">Выберите в списке диспетчер подключений OLE DB или щелкните \<**New connection...**>, чтобы создать подключение.</span><span class="sxs-lookup"><span data-stu-id="a2e45-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="a2e45-108">**См. также:** [Диспетчер подключений OLE DB](connection-manager/ole-db-connection-manager.md), [Настройка диспетчера подключений OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="a2e45-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="a2e45-109">**DestinationTable**</span><span class="sxs-lookup"><span data-stu-id="a2e45-109">**DestinationTable**</span></span>  
 <span data-ttu-id="a2e45-110">Введите имя целевой таблицы или представления или выберите таблицу или представление из списка.</span><span class="sxs-lookup"><span data-stu-id="a2e45-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="a2e45-111">**Формат**</span><span class="sxs-lookup"><span data-stu-id="a2e45-111">**Format**</span></span>  
 <span data-ttu-id="a2e45-112">Выберите источник формата для массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="a2e45-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="a2e45-113">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a2e45-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="a2e45-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a2e45-114">Value</span></span>|<span data-ttu-id="a2e45-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a2e45-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2e45-116">**Использовать файл**</span><span class="sxs-lookup"><span data-stu-id="a2e45-116">**Use File**</span></span>|<span data-ttu-id="a2e45-117">Выберите файл, содержащий спецификацию формата.</span><span class="sxs-lookup"><span data-stu-id="a2e45-117">Select a file containing the format specification.</span></span> <span data-ttu-id="a2e45-118">При выборе этого параметра отображается динамический параметр **FormatFile**.</span><span class="sxs-lookup"><span data-stu-id="a2e45-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="a2e45-119">**Указать**</span><span class="sxs-lookup"><span data-stu-id="a2e45-119">**Specify**</span></span>|<span data-ttu-id="a2e45-120">Укажите формат.</span><span class="sxs-lookup"><span data-stu-id="a2e45-120">Specify the format.</span></span> <span data-ttu-id="a2e45-121">При выборе этого параметра отображаются динамические параметры `RowDelimiter` и `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="a2e45-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="a2e45-122">**Файл**</span><span class="sxs-lookup"><span data-stu-id="a2e45-122">**File**</span></span>  
 <span data-ttu-id="a2e45-123">Выберите в списке диспетчер подключений обычных или неструктурированных файлов либо щелкните \<**New connection...**>, чтобы создать подключение.</span><span class="sxs-lookup"><span data-stu-id="a2e45-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="a2e45-124">Расположение файла задается относительно компонента SQL Server Database Engine, указанного в диспетчере соединений для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="a2e45-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="a2e45-125">Доступ к тестовому файлу можно получить с помощью компонента SQL Server Database Engine на локальном жестком диске на сервере или через общий диск или сопоставленный диск относительно SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2e45-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="a2e45-126">Этот файл не имеет доступа к среде выполнения служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="a2e45-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="a2e45-127">Если пользователь осуществляет доступ к исходному файлу с помощью диспетчера соединений с неструктурированным файлом, в задаче «Массовая вставка» не используется формат, указанный в диспетчере соединений с неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="a2e45-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="a2e45-128">Вместо этого задача "Массовая вставка" использует либо формат, указанный в файле форматирования, либо значения свойств задачи RowDelimiter и ColumnDelimiter.</span><span class="sxs-lookup"><span data-stu-id="a2e45-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="a2e45-129">**См. также:** [Диспетчер подключений](connection-manager/file-connection-manager.md), [Редактор диспетчера соединения файлов](../../2014/integration-services/file-connection-manager-editor.md), [Диспетчер соединений с неструктурированными файлами](connection-manager/flat-file-connection-manager.md), [Редактор диспетчера соединений с неструктурированными файлами (страница "Общие")](general-page-of-integration-services-designers-options.md), [Редактор диспетчера соединений с неструктурированными файлами (страница "Столбцы")](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Редактор диспетчера соединений с неструктурированными файлами (страница "Дополнительно")](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="a2e45-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="a2e45-130">**Обновить таблицы**</span><span class="sxs-lookup"><span data-stu-id="a2e45-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="a2e45-131">Обновите список таблиц и представлений.</span><span class="sxs-lookup"><span data-stu-id="a2e45-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="a2e45-132">Динамические параметры формата</span><span class="sxs-lookup"><span data-stu-id="a2e45-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="a2e45-133">Формат = Использовать файл</span><span class="sxs-lookup"><span data-stu-id="a2e45-133">Format = Use File</span></span>  
 <span data-ttu-id="a2e45-134">**FormatFile**</span><span class="sxs-lookup"><span data-stu-id="a2e45-134">**FormatFile**</span></span>  
 <span data-ttu-id="a2e45-135">Введите путь к файлу форматирования или нажмите кнопку с многоточием **(...)** для поиска этого файла.</span><span class="sxs-lookup"><span data-stu-id="a2e45-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="a2e45-136">Формат = Указать</span><span class="sxs-lookup"><span data-stu-id="a2e45-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="a2e45-137">Укажите разделитель строк в файле источника.</span><span class="sxs-lookup"><span data-stu-id="a2e45-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="a2e45-138">Значением по умолчанию является **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="a2e45-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="a2e45-139">Укажите разделитель столбцов в файле источника.</span><span class="sxs-lookup"><span data-stu-id="a2e45-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="a2e45-140">Значение по умолчанию составляет **Табуляция**.</span><span class="sxs-lookup"><span data-stu-id="a2e45-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e45-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2e45-141">See Also</span></span>  
 <span data-ttu-id="a2e45-142">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a2e45-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a2e45-143">[Редактор задачи "групповые вставки" &#40;общие&#41;страницы](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="a2e45-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="a2e45-144">[Редактор задачи "операции с массовыми вставками" &#40;параметры&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="a2e45-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="a2e45-145">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a2e45-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="a2e45-146">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a2e45-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="a2e45-147">Поток управления</span><span class="sxs-lookup"><span data-stu-id="a2e45-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
