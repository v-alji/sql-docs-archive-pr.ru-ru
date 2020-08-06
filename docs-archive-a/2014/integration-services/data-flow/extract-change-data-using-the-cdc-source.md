---
title: Извлечение информации об изменениях данных с помощью источника CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 604fbafb-15fa-4d11-8487-77d7b626eed8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ef981a22e286f519c9b93b3181b47df43321548b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751340"
---
# <a name="extract-change-data-using-the-cdc-source"></a><span data-ttu-id="0b7fa-102">Извлечение информации об изменениях данных с помощью источника CDC</span><span class="sxs-lookup"><span data-stu-id="0b7fa-102">Extract Change Data Using the CDC Source</span></span>
  <span data-ttu-id="0b7fa-103">Чтобы можно было добавить и настроить источник CDC, пакет уже должен включать по крайней мере одну задачу «Поток данных» и задачу «Управление CDC».</span><span class="sxs-lookup"><span data-stu-id="0b7fa-103">To add and configure a CDC source, the package must already include at least one Data Flow task and a CDC Control task.</span></span>  
  
 <span data-ttu-id="0b7fa-104">Дополнительные сведения о задаче «Управление CDC» см. в разделе [CDC Control Task](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-104">For more information about the CDC Control task, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="0b7fa-105">Дополнительные сведения об источнике CDC см. в разделе [CDC Source](cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-105">For more information about the CDC source, see [CDC Source](cdc-source.md).</span></span>  
  
### <a name="to-extract-change-data-using-a-cdc-source"></a><span data-ttu-id="0b7fa-106">Извлечение информации об изменениях с использованием источника CDC</span><span class="sxs-lookup"><span data-stu-id="0b7fa-106">To extract change data using a CDC source</span></span>  
  
1.  <span data-ttu-id="0b7fa-107">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0b7fa-108">В Обозревателе решений дважды щелкните пакет, чтобы его открыть.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b7fa-109">Щелкните вкладку **Поток данных** , а затем **Панель элементов**и перетащите источник CDC в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC source to the design surface.</span></span>  
  
4.  <span data-ttu-id="0b7fa-110">Дважды щелкните источник CDC.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-110">Double-click the CDC source.</span></span>  
  
5.  <span data-ttu-id="0b7fa-111">В диалоговом окне **Редактор источников CDC** , на странице **Диспетчер соединений** выберите существующий диспетчер соединений ADO.NET из списка или щелкните **Создать** , чтобы создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-111">In the **CDC Source Editor** dialog box, on the **Connection Manager** page, select an existing ADO.NET connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="0b7fa-112">Соединение должно быть установлено с базой данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , содержащей таблицы изменений, которые должны быть считаны.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-112">The connection should be to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the change tables to read.</span></span>  
  
6.  <span data-ttu-id="0b7fa-113">Выберите **таблицу CDC** , в которой необходимо обработать изменения.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-113">Select the **CDC table** where you want to process changes.</span></span>  
  
7.  <span data-ttu-id="0b7fa-114">Выберите или введите имя **экземпляра отслеживания CDC** в сочетании с таблицей CDC, которая должна быть считана.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-114">Select or type in the name of the **CDC capture instance** with the CDC table to be read.</span></span>  
  
     <span data-ttu-id="0b7fa-115">Отслеживаемая исходная таблица может иметь один или два отслеживаемых экземпляра для обеспечения возможности беспрепятственных переходов определения таблицы во время изменений схемы.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-115">A captured source table can have one or two captured instances to handle seamless transitioning of table definition through schema changes.</span></span> <span data-ttu-id="0b7fa-116">Если для исходной таблицы отслеживания определено больше одного экземпляра отслеживания, выберите экземпляр отслеживания, который должен здесь использоваться.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-116">If more than one capture instance is defined for the source table being captured, select the capture instance you want to use here.</span></span> <span data-ttu-id="0b7fa-117">По умолчанию экземпляр отслеживания для таблицы [схема].[таблица] имеет имя \<schema>_\<table>, но фактически используемые экземпляры отслеживания могут иметь другие имена.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-117">The default capture instance name for a table [schema].[table] is \<schema>_\<table> but that actual capture instance names in use may be different.</span></span> <span data-ttu-id="0b7fa-118">Таблицей, откуда фактически считываются данные, является таблица CDC **cdc .\<capture-instance>_CT**.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-118">The actual table that is read from is the CDC table **cdc .\<capture-instance>_CT**.</span></span>  
  
8.  <span data-ttu-id="0b7fa-119">Выберите режим обработки, который в наилучшей степени соответствует конкретным потребностям обработки.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-119">Select the processing mode that best handles your processing needs.</span></span> <span data-ttu-id="0b7fa-120">Возможными вариантами являются следующие.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-120">The possible options are:</span></span>  
  
    -   <span data-ttu-id="0b7fa-121">**Все**: возвращает изменения в текущем диапазоне CDC без значений **перед обновлением** .</span><span class="sxs-lookup"><span data-stu-id="0b7fa-121">**All**: Returns the changes in the current CDC range without the **Before Update** values.</span></span>  
  
    -   <span data-ttu-id="0b7fa-122">**Все со старыми значениями**: возвращает изменения в текущем диапазоне обработки CDC, включая старые значения (**перед обновлением**).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-122">**All with old values**: Returns the changes in the current CDC processing range including the old values (**Before Update**).</span></span> <span data-ttu-id="0b7fa-123">С каждой операции Update связаны две строки: одна со значениями перед обновлением и еще одна со значениями после обновления.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-123">For each Update operation, there will be two rows, one with the before-update values and one with the after-update value.</span></span>  
  
    -   <span data-ttu-id="0b7fa-124">**Суммарные**: возвращает только по одной строке изменения в расчете на каждую исходную строку, измененную в текущем диапазоне обработки CDC.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-124">**Net**: Returns only one change row per source row modified in the current CDC processing range.</span></span> <span data-ttu-id="0b7fa-125">Если исходная строка была обновлена несколько раз, вырабатывается комбинированное изменение (например, результат операций insert и update формируется как единственное обновление, а результат операций update и delete — как единственное удаление).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-125">If a source row was updated multiple times, the combined change is produced (for example, insert+update is produced as a single update and update+delete is produced as a single delete).</span></span> <span data-ttu-id="0b7fa-126">При работе в режиме обработки изменений «Суммарные» обеспечивается возможность разбивать изменения на выводы Delete, Insert и Update и обрабатывать их параллельно, поскольку единственная исходная строка появляется более чем в одном выводе.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-126">When working in Net change processing mode, it is possible to split the changes to Delete, Insert and Update outputs and handle them in parallel because the single source row appears in more than one output.</span></span>  
  
    -   <span data-ttu-id="0b7fa-127">**Суммарные с маской обновления**: этот режим аналогичен обычному режиму "Суммарные", но также добавляет столбцы логических значений, имена которым присваиваются по шаблону **__$\<column-name>\__Changed**, указывающие на измененные столбцы в текущей строке изменения.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-127">**Net with update mask**: This mode is similar to the regular Net mode but it also adds boolean columns with the name pattern **__$\<column-name>\__Changed** that indicate changed columns in the current change row.</span></span>  
  
    -   <span data-ttu-id="0b7fa-128">**Суммарные со слиянием**: этот режим аналогичен обычному режиму "Суммарные", но с операциями Insert и Update, объединенными в одной операции Merge (UPSERT).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-128">**Net with merge**: This mode is similar to the regular Net mode but with Insert and Update operations merged into a single Merge operation (UPSERT).</span></span>  
  
9. <span data-ttu-id="0b7fa-129">Выберите строковую переменную пакета службы SSIS, в которой хранится состояние CDC для текущего контекста CDC.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-129">Select the SSIS string package variable that maintains the CDC state for the current CDC context.</span></span> <span data-ttu-id="0b7fa-130">Дополнительные сведения о переменной состояния CDC см. в разделе [Определение переменной состояния](define-a-state-variable.md).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-130">For more information about the CDC state variable, see [Define a State Variable](define-a-state-variable.md).</span></span>  
  
10. <span data-ttu-id="0b7fa-131">Установите флажок **Включить столбец индикатора повторной обработки** , чтобы создать специальный выходной столбец с именем **__$reprocessing**.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-131">Select the **Include reprocessing indicator column** check box to create a special output column called **__$reprocessing**.</span></span> <span data-ttu-id="0b7fa-132">Этот столбец имеет значение **true** , если диапазон обработки CDC перекрывается с начальным диапазоном обработки (с диапазоном номеров LSN, соответствующих периоду начальной загрузки) или если диапазон обработки CDC подвергается повторной обработке вследствие ошибки в предыдущем прогоне.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-132">This column has a value of **true** when the CDC processing range overlaps with the initial processing range (the range of LSNs corresponding to the period of initial load) or when a CDC processing range is reprocessed following an error in a previous run.</span></span> <span data-ttu-id="0b7fa-133">Этот столбец индикатора позволяет разработчику служб SSIS трактовать ошибки иначе при повторной обработке изменений (например, пропускать действия наподобие удаления несуществующей строки или вставки, которая окончилась неудачей из-за дублирующегося ключа).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-133">This indicator column lets the SSIS developer handle errors differently when reprocessing changes (for example, actions such as a delete of a non-existing row and an insert that failed on a duplicate key can be ignored).</span></span>  
  
     <span data-ttu-id="0b7fa-134">Дополнительные сведения см. в статье [CDC Source Custom Properties](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0b7fa-134">For more information, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
11. <span data-ttu-id="0b7fa-135">Чтобы обновить сопоставление между внешними и выходными столбцами, щелкните **Столбцы** и выберите другие столбцы в списке **Внешний столбец** .</span><span class="sxs-lookup"><span data-stu-id="0b7fa-135">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
12. <span data-ttu-id="0b7fa-136">Можно также обновить значения выходных столбцов, удаляя значения в списке **Выходной столбец** .</span><span class="sxs-lookup"><span data-stu-id="0b7fa-136">Optionally update the values of the output columns by deleting values in the **Output Column** list.</span></span>  
  
13. <span data-ttu-id="0b7fa-137">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-137">To configure the error output, click **Error Output**.</span></span>  
  
14. <span data-ttu-id="0b7fa-138">Можно щелкнуть **Предварительный просмотр** , чтобы рассмотреть до 200 строк данных, извлеченных источником CDC.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-138">You can click **Preview** to view up to 200 rows of data extracted by the CDC source.</span></span>  
  
15. <span data-ttu-id="0b7fa-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b7fa-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7fa-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b7fa-140">See Also</span></span>  
 <span data-ttu-id="0b7fa-141">[Редактор источника "CDC" (страница "Диспетчер соединений")](../cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0b7fa-141">[CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="0b7fa-142">[Редактор источника "CDC" (страница "Столбцы")](../cdc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="0b7fa-142">[CDC Source Editor &#40;Columns Page&#41;](../cdc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="0b7fa-143">Редактор источника "CDC" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="0b7fa-143">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
  
