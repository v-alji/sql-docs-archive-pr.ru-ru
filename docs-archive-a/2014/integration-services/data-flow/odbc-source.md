---
title: Источник ODBC | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657195"
---
# <a name="odbc-source"></a><span data-ttu-id="d6136-102">ODBC-источник</span><span class="sxs-lookup"><span data-stu-id="d6136-102">ODBC Source</span></span>
  <span data-ttu-id="d6136-103">Источник ODBC извлекает данные из базы данных с поддержкой ODBC с использованием таблицы базы данных, представления или инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="d6136-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="d6136-104">В источнике ODBC предусмотрены следующие режимы доступа к данным для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="d6136-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="d6136-105">Таблица или представление.</span><span class="sxs-lookup"><span data-stu-id="d6136-105">A table or view.</span></span>  
  
-   <span data-ttu-id="d6136-106">Результат выполнения инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="d6136-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="d6136-107">В источнике используется диспетчер соединений ODBC, который указывает применяемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="d6136-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="d6136-108">Источник ODBC включает выходные столбцы исходных данных.</span><span class="sxs-lookup"><span data-stu-id="d6136-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="d6136-109">При сопоставлении в назначении ODBC выходных столбцов со столбцами назначения могут возникнуть ошибки, если не задано сопоставление выходных столбцов с целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="d6136-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="d6136-110">Сопоставлены могут быть столбцы различных типов, однако если выходные данные несовместимы с назначением, то во время выполнения возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="d6136-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="d6136-111">В зависимости от настройки поведения в случае ошибки, ошибка может быть пропущена, может быть вызван сбой, или строка может быть отправлена в вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="d6136-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="d6136-112">Источник ODBC имеет один обычный вывод и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="d6136-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="d6136-113">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="d6136-113">Error Handling</span></span>  
 <span data-ttu-id="d6136-114">Источник ODBC имеет вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="d6136-114">The ODBC source has an error output.</span></span> <span data-ttu-id="d6136-115">Вывод ошибок компонента включает следующие выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="d6136-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="d6136-116">**Код ошибки**. Номер, который соответствует текущей ошибке.</span><span class="sxs-lookup"><span data-stu-id="d6136-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="d6136-117">См. документацию для базы данных с поддержкой ODBC, которая используется для получения списка ошибок.</span><span class="sxs-lookup"><span data-stu-id="d6136-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="d6136-118">Список кодов ошибок служб SSIS см. в «Справочнике по кодам ошибок и сообщениям служб SIS».</span><span class="sxs-lookup"><span data-stu-id="d6136-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="d6136-119">**Столбец с ошибкой**. Входной столбец, вызывающий ошибку (это относится к ошибкам преобразования).</span><span class="sxs-lookup"><span data-stu-id="d6136-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="d6136-120">Стандартные устройства вывода столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="d6136-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="d6136-121">В зависимости от настройки поведения в случае ошибки, источник ODBC поддерживает возврат ошибок (преобразование данных, усечение), которые обнаруживаются в процессе извлечения в выводе ошибок.</span><span class="sxs-lookup"><span data-stu-id="d6136-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="d6136-122">Дополнительные сведения см. в статье [Редактор назначения ODBC (страница "Диспетчер соединений")](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="d6136-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="d6136-123">Поддержка типов данных</span><span class="sxs-lookup"><span data-stu-id="d6136-123">Data Type Support</span></span>  
 <span data-ttu-id="d6136-124">Сведения о типах данных, поддерживаемых источником ODBC, см. в документе «Соединитель для ODBC» компании Attunity.</span><span class="sxs-lookup"><span data-stu-id="d6136-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="d6136-125">Параметры извлечения</span><span class="sxs-lookup"><span data-stu-id="d6136-125">Extract Options</span></span>  
 <span data-ttu-id="d6136-126">Источник ODBC работает в пакетном ( **Batch** ) или построчном ( **Row-by-Row** ) режиме.</span><span class="sxs-lookup"><span data-stu-id="d6136-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="d6136-127">Используемый режим определяется свойством **FetchMethod** .</span><span class="sxs-lookup"><span data-stu-id="d6136-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="d6136-128">Описания режимов приведены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="d6136-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="d6136-129">**Batch**: компонент предпринимает попытку использовать наиболее эффективный метод выборки на основе предполагаемых возможностей поставщика ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="d6136-130">Для наиболее современных поставщиков ODBC этим методом является SQLFetchScroll с привязкой массива (где размер массива определяется свойством **BatchSize** ).</span><span class="sxs-lookup"><span data-stu-id="d6136-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="d6136-131">Если выбран режим **Batch** , а поставщик не поддерживает этот способ выборки, назначение ODBC автоматически переключается на режим **Row-by-row** .</span><span class="sxs-lookup"><span data-stu-id="d6136-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="d6136-132">**Row-by Row**: компонент использует метод SQLFetch для получения строк друг за другом.</span><span class="sxs-lookup"><span data-stu-id="d6136-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="d6136-133">Дополнительные сведения о свойстве **FetchMethod** см. в разделе [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d6136-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="d6136-134">Parallelism</span><span class="sxs-lookup"><span data-stu-id="d6136-134">Parallelism</span></span>  
 <span data-ttu-id="d6136-135">Какие-либо ограничения на количество исходных компонентов ODBC, которые могут запускаться параллельно по отношению к одной и той же таблице или к разным таблицам, на одном и том же компьютере или на разных компьютерах (кроме обычных глобальных предельных параметров сеанса), отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d6136-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="d6136-136">Однако количество параллельных соединений через поставщика может быть ограничено в используемом поставщике ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="d6136-137">Эти ограничения задают количество параллельных экземпляров, которые могут поддерживаться для источника ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="d6136-138">Разработчик служб SSIS должен знать ограничения всех используемых поставщиков ODBC и учитывать их при построении пакетов служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="d6136-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="d6136-139">Устранение нарушений в работе источника ODBC</span><span class="sxs-lookup"><span data-stu-id="d6136-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="d6136-140">Предусмотрена возможность вести журнал вызовов к внешним поставщикам данных, выполняемых источником ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="d6136-141">Эту возможность ведения журнала можно использовать для устранения нарушений, связанных с загрузкой данных из внешних источников данных, выполняемой источником ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="d6136-142">Для ведения журнала вызовов к внешним поставщикам данных, выполняемых источником ODBC, включите трассировку диспетчера драйвера ODBC.</span><span class="sxs-lookup"><span data-stu-id="d6136-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="d6136-143">Дополнительные сведения см. в документации Майкрософт по теме *Как формировать трассировку ODBC с помощью администратора источника данных ODBC*.</span><span class="sxs-lookup"><span data-stu-id="d6136-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="d6136-144">Настройка ODBC-источника</span><span class="sxs-lookup"><span data-stu-id="d6136-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="d6136-145">Источник ODBC вы можете настраивать программным путем или с помощью конструктора SSIS.</span><span class="sxs-lookup"><span data-stu-id="d6136-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="d6136-146">Дополнительные сведения см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="d6136-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d6136-147">Редактор источника ODBC (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="d6136-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d6136-148">Редактор источника ODBC (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="d6136-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="d6136-149">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="d6136-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="d6136-150">Диалоговое окно **Расширенный редактор** содержит свойства, которые могут быть заданы программным путем.</span><span class="sxs-lookup"><span data-stu-id="d6136-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="d6136-151">Открытие диалогового окна **Расширенный редактор** .</span><span class="sxs-lookup"><span data-stu-id="d6136-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="d6136-152">На экране **Поток данных** конкретного проекта [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] щелкните правой кнопкой мыши источник ODBC и выберите пункт **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="d6136-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="d6136-153">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне «Расширенный редактор», см. в разделе [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d6136-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6136-154">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d6136-154">In This Section</span></span>  
  
-   [<span data-ttu-id="d6136-155">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="d6136-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="d6136-156">Редактор источника ODBC (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="d6136-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="d6136-157">Редактор источника ODBC (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="d6136-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d6136-158">Извлечение данных с помощью источника ODBC</span><span class="sxs-lookup"><span data-stu-id="d6136-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="d6136-159">Пользовательские свойства источника «ODBC»</span><span class="sxs-lookup"><span data-stu-id="d6136-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
