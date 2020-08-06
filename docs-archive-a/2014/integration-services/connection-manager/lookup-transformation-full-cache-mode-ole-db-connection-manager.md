---
title: Реализация преобразования «Уточняющий запрос» в режиме полного кэширования с помощью диспетчера соединений OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667362"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="18ab8-102">Реализация преобразования «Уточняющий запрос» в режиме полного кэширования с помощью диспетчера соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="18ab8-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="18ab8-103">Можно настроить преобразование «Уточняющий запрос», чтобы использовать режим полного кэширования и диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="18ab8-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="18ab8-104">В режиме полного кэширования эталонный набор данных загружается в кэш еще до запуска преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="18ab8-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="18ab8-105">Преобразование «Уточняющий запрос» выполняет уточняющие запросы, соединяя данные из входных столбцов подключенного источника данных и данные из столбцов в эталонном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="18ab8-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="18ab8-106">Дополнительные сведения см. в разделе [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="18ab8-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="18ab8-107">При настройке преобразования «Уточняющий запрос» для использования диспетчера соединений OLE DB, нужно выбрать таблицу, представление или SQL-запрос для создания эталонного набора данных.</span><span class="sxs-lookup"><span data-stu-id="18ab8-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="18ab8-108">Реализация преобразования «Уточняющий запрос» с полным кэшированием с помощью диспетчера соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="18ab8-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="18ab8-109">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий нужный пакет, а затем дважды щелкните этот пакет в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="18ab8-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="18ab8-110">Щелкните вкладку **Поток данных** , а затем перетащите преобразование «Уточняющий запрос» из **области элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="18ab8-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="18ab8-111">Подключите преобразование «Уточняющий запрос» к потоку данных, перетащив соединитель из источника или предыдущего преобразования в преобразование «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="18ab8-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18ab8-112">Преобразование «Уточняющий запрос» может не пройти проверку, если оно соединено с неструктурированным файлом, в котором содержится пустое поле данных.</span><span class="sxs-lookup"><span data-stu-id="18ab8-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="18ab8-113">Успешность проверки преобразования зависит от того, включено ли в диспетчере соединений для неструктурированного файла сохранение значений NULL.</span><span class="sxs-lookup"><span data-stu-id="18ab8-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="18ab8-114">Чтобы гарантировать успешность проверки преобразования «Уточняющий запрос», выберите в **редакторе источника «неструктурированный файл»** на странице **Диспетчер соединений**параметр **Оставлять значения NULL из источника в потоке данных** .</span><span class="sxs-lookup"><span data-stu-id="18ab8-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="18ab8-115">Чтобы настроить компонент, дважды щелкните источник или предыдущее преобразование.</span><span class="sxs-lookup"><span data-stu-id="18ab8-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="18ab8-116">Дважды щелкните преобразование "Уточняющий запрос", а затем в окне **Редактор преобразования "Уточняющий запрос"** на странице **Общие** выберите **Полное кэширование**.</span><span class="sxs-lookup"><span data-stu-id="18ab8-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="18ab8-117">В области **Тип соединения** выберите **Диспетчер соединений OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="18ab8-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="18ab8-118">В списке **Укажите метод обработки строк без совпадающих элементов** выберите параметр обработки ошибок для строк без совпадающих элементов.</span><span class="sxs-lookup"><span data-stu-id="18ab8-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="18ab8-119">На странице «Соединение» выберите диспетчер соединений из списка **Диспетчер соединений OLE DB** или нажмите кнопку **Создать** , чтобы создать новый диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="18ab8-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="18ab8-120">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="18ab8-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="18ab8-121">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="18ab8-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="18ab8-122">Выберите параметр **Использовать таблицу или представление**, а затем выберите таблицу или представление; либо нажмите кнопку **Создать** , чтобы создать таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="18ab8-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="18ab8-123">-или-</span><span class="sxs-lookup"><span data-stu-id="18ab8-123">-or-</span></span>  
  
    -   <span data-ttu-id="18ab8-124">Щелкните мышью **Использовать результаты SQL-запроса**и введите запрос в окне **Команда SQL** или щелкните **Создать запрос** для создания запроса с помощью графических средств, предоставляемых **построителем запросов** .</span><span class="sxs-lookup"><span data-stu-id="18ab8-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="18ab8-125">-или-</span><span class="sxs-lookup"><span data-stu-id="18ab8-125">-or-</span></span>  
  
    -   <span data-ttu-id="18ab8-126">Можно также щелкнуть **Обзор** для импорта инструкции SQL из файла.</span><span class="sxs-lookup"><span data-stu-id="18ab8-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="18ab8-127">Для проверки SQL-запроса щелкните **Анализ запроса**.</span><span class="sxs-lookup"><span data-stu-id="18ab8-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="18ab8-128">Чтобы просмотреть образец, нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="18ab8-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="18ab8-129">Перейдите на страницу **Столбцы** и перетащите хотя бы один из столбцов в списке **Доступные входные столбцы** в столбец из списка **Доступные уточняющие столбцы** .</span><span class="sxs-lookup"><span data-stu-id="18ab8-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18ab8-130">Преобразование «Уточняющий запрос» автоматически сопоставляет столбцы, которые обладают одинаковыми названиями и типами данных.</span><span class="sxs-lookup"><span data-stu-id="18ab8-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18ab8-131">Типы данных сопоставляемых столбцов должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="18ab8-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="18ab8-132">Дополнительные сведения см. в разделе [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="18ab8-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="18ab8-133">Включите столбцы подстановки в выходные данные, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="18ab8-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="18ab8-134">В списке **Доступные столбцы подстановки** .</span><span class="sxs-lookup"><span data-stu-id="18ab8-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="18ab8-135">выберите столбцы.</span><span class="sxs-lookup"><span data-stu-id="18ab8-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="18ab8-136">Затем в списке **Операция поиска** укажите, будут ли значения из столбцов подстановки заменять значения входных столбцов или они будут записаны в новый столбец.</span><span class="sxs-lookup"><span data-stu-id="18ab8-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="18ab8-137">Чтобы настроить вывод ошибок, перейдите на страницу **Вывод ошибок** и задайте параметры обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="18ab8-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="18ab8-138">Дополнительные сведения см. в разделе [Редактор преобразования "Уточняющий запрос" (страница "Вывод ошибок")](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="18ab8-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="18ab8-139">Нажмите кнопку **ОК** , чтобы сохранить изменения в преобразовании «Уточняющий запрос», а затем запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="18ab8-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ab8-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="18ab8-140">See Also</span></span>  
 <span data-ttu-id="18ab8-141">[Реализация преобразования "Уточняющий запрос" в режиме полного кэширования с помощью преобразования диспетчера подключений с кэшем](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18ab8-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="18ab8-142">[Реализация уточняющего запроса в режиме "Частичное кэширование" или "Без кэширования"](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="18ab8-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="18ab8-143">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="18ab8-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
