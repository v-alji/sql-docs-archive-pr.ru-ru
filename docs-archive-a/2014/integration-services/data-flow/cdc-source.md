---
title: Источник CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667841"
---
# <a name="cdc-source"></a><span data-ttu-id="bc129-102">CDC-источник</span><span class="sxs-lookup"><span data-stu-id="bc129-102">CDC Source</span></span>
  <span data-ttu-id="bc129-103">Источник CDC считывает диапазон информации об изменениях из таблиц изменений [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и доставляет изменения другим нижестоящим компонентам SSIS.</span><span class="sxs-lookup"><span data-stu-id="bc129-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="bc129-104">Диапазон информации об изменениях, считанный источником CDC, именуется диапазоном обработки CDC и определяется задачей «Управление CDC», которая выполняется до запуска текущего потока данных.</span><span class="sxs-lookup"><span data-stu-id="bc129-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="bc129-105">Диапазон обработки CDC определяется с помощью значения переменной пакета, которая поддерживает состояние обработки CDC для группы таблиц.</span><span class="sxs-lookup"><span data-stu-id="bc129-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="bc129-106">Источник CDC извлекает данные из базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием таблицы базы данных, представления или инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="bc129-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="bc129-107">Источник CDC использует следующие конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bc129-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="bc129-108">Диспетчер соединений ADO.NET [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для получения доступа к базе данных CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc129-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="bc129-109">Дополнительные сведения о настройке соединения с источником CDC см. в разделе [Редактор источника "CDC" (страница "Диспетчер соединений")](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="bc129-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="bc129-110">Таблица, включенная для CDC.</span><span class="sxs-lookup"><span data-stu-id="bc129-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="bc129-111">Имя экземпляра отслеживания выбранной таблицы (если таковых существует несколько).</span><span class="sxs-lookup"><span data-stu-id="bc129-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="bc129-112">Режим обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="bc129-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="bc129-113">Имя переменной пакета состояния CDC, на основе которой определен диапазон обработки CDC.</span><span class="sxs-lookup"><span data-stu-id="bc129-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="bc129-114">Источник CDC не изменяет значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bc129-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="bc129-115">Данные, возвращенные источником CDC, являются теми же, что возвращают следующие функции CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** или **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (если они доступны).</span><span class="sxs-lookup"><span data-stu-id="bc129-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="bc129-116">Единственным необязательным добавлением является столбец **__$initial_processing** , который указывает, может ли текущий диапазон обработки перекрывать диапазон начальной загрузки таблицы.</span><span class="sxs-lookup"><span data-stu-id="bc129-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="bc129-117">Дополнительные сведения о начальной обработке см. в разделе [CDC Control Task](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="bc129-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="bc129-118">Источник CDC имеет один обычный вывод и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="bc129-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="bc129-119">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="bc129-119">Error Handling</span></span>  
 <span data-ttu-id="bc129-120">Источник CDC имеет вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="bc129-120">The CDC source has an error output.</span></span> <span data-ttu-id="bc129-121">Вывод ошибок компонента включает следующие выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="bc129-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="bc129-122">**Код ошибки**. Значение всегда равно -1.</span><span class="sxs-lookup"><span data-stu-id="bc129-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="bc129-123">**Столбец с ошибкой**. Входной столбец, вызывающий ошибку (это относится к ошибкам преобразования).</span><span class="sxs-lookup"><span data-stu-id="bc129-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="bc129-124">**Столбцы строки с ошибкой**. Данные записи, которые вызывают ошибку.</span><span class="sxs-lookup"><span data-stu-id="bc129-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="bc129-125">В зависимости от настройки поведения в случае ошибки, источник CDC поддерживает возврат ошибок (преобразование данных, усечение), которые обнаруживаются в процессе извлечения в выводе ошибок.</span><span class="sxs-lookup"><span data-stu-id="bc129-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="bc129-126">Дополнительные сведения см. в разделе [Редактор источника "CDC" (страница "Вывод ошибок")](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="bc129-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="bc129-127">Поддержка типов данных</span><span class="sxs-lookup"><span data-stu-id="bc129-127">Data Type Support</span></span>  
 <span data-ttu-id="bc129-128">Компонент источника CDC для Microsoft поддерживает все типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые сопоставлены с верными типами данных SSIS.</span><span class="sxs-lookup"><span data-stu-id="bc129-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="bc129-129">Устранение нарушений в работе с источником CDC</span><span class="sxs-lookup"><span data-stu-id="bc129-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="bc129-130">Ниже приведена информация об устранении нарушений в работе с источником CDC.</span><span class="sxs-lookup"><span data-stu-id="bc129-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="bc129-131">Этот скрипт используется для выявления проблем и воспроизведения их в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc129-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="bc129-132">Операцией источника CDC управляет операция задачи «Управление CDC», выполняемая перед вызовом источника CDC.</span><span class="sxs-lookup"><span data-stu-id="bc129-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="bc129-133">Задача «Управление CDC» подготавливает значение переменной пакета состояния CDC для включения начального и конечного номеров LSN.</span><span class="sxs-lookup"><span data-stu-id="bc129-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="bc129-134">Задача выполняет функции, эквивалентные следующему скрипту:</span><span class="sxs-lookup"><span data-stu-id="bc129-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="bc129-135">где:</span><span class="sxs-lookup"><span data-stu-id="bc129-135">where:</span></span>  
  
-   <span data-ttu-id="bc129-136">\<cdc-enabled-database-name> — это имя базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], содержащей таблицы изменений.</span><span class="sxs-lookup"><span data-stu-id="bc129-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="bc129-137">\<value-from-state-cs> — это значение, которое появляется в переменной состояния CDC в виде CS/\<value-from-state-cs>/ (CS означает Current-processing-range-Start — начало текущего диапазона обработки).</span><span class="sxs-lookup"><span data-stu-id="bc129-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="bc129-138">\<value-from-state-ce> — это значение, которое появляется в переменной состояния CDC в виде CE/\<value-from-state-cs>/ (CE означает Current-processing-range-End — конец текущего диапазона обработки).</span><span class="sxs-lookup"><span data-stu-id="bc129-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="bc129-139">\<mode> — это режимы обработки CDC.</span><span class="sxs-lookup"><span data-stu-id="bc129-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="bc129-140">Режимы обработки могут иметь одно из следующих значений: **Все**, **Все со старыми значениями**, **Суммарные**, **Суммарные с маской обновления**, **Суммарные со слиянием**.</span><span class="sxs-lookup"><span data-stu-id="bc129-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="bc129-141">Этот скрипт позволяет выявлять проблемы путем воспроизведения их в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], где можно легко воспроизводить и идентифицировать ошибки.</span><span class="sxs-lookup"><span data-stu-id="bc129-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="bc129-142">Сообщение об ошибке SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc129-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="bc129-143">Следующее сообщение может быть возвращено [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bc129-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="bc129-144">**Для функции или процедуры cdc.fn_cdc_get_net_changes_\<..> задано недостаточное количество аргументов.**</span><span class="sxs-lookup"><span data-stu-id="bc129-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="bc129-145">Эта ошибка не указывает, что отсутствует какой-то аргумент.</span><span class="sxs-lookup"><span data-stu-id="bc129-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="bc129-146">Она означает, что начало или конец диапазона значений номеров LSN в переменной состояния CDC является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="bc129-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="bc129-147">Настройка CDC-источника</span><span class="sxs-lookup"><span data-stu-id="bc129-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="bc129-148">Источник CDC можно настраивать программным путем или с помощью конструктора служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="bc129-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="bc129-149">Дополнительные сведения см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="bc129-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bc129-150">Редактор источника "CDC" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="bc129-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="bc129-151">Редактор источника "CDC" (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="bc129-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="bc129-152">Редактор источника "CDC" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="bc129-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="bc129-153">Диалоговое окно **Расширенный редактор** содержит свойства, которые могут быть заданы программным путем.</span><span class="sxs-lookup"><span data-stu-id="bc129-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="bc129-154">Открытие диалогового окна **Расширенный редактор** .</span><span class="sxs-lookup"><span data-stu-id="bc129-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="bc129-155">На экране **Поток данных** вашего проекта [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] щелкните правой кнопкой мыши источник CDC и выберите элемент **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="bc129-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="bc129-156">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Расширенный редактор** , см. в разделе [CDC Source Custom Properties](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bc129-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc129-157">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bc129-157">In This Section</span></span>  
  
-   [<span data-ttu-id="bc129-158">Редактор источника "CDC" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="bc129-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="bc129-159">Редактор источника "CDC" (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="bc129-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="bc129-160">Редактор источника "CDC" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="bc129-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="bc129-161">Пользовательские свойства источника «CDC»</span><span class="sxs-lookup"><span data-stu-id="bc129-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="bc129-162">Извлечение информации об изменениях данных с помощью источника «CDC»</span><span class="sxs-lookup"><span data-stu-id="bc129-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="bc129-163">См. также</span><span class="sxs-lookup"><span data-stu-id="bc129-163">Related Content</span></span>  
  
-   <span data-ttu-id="bc129-164">Запись в блоге [Режимы обработки для источника CDC](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/)на сайте mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="bc129-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  
