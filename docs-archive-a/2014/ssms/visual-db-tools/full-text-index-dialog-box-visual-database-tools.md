---
title: Диалоговое окно "Полнотекстовые индексы" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750403"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="919d7-102">Диалоговое окно «Полнотекстовые индексы» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="919d7-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="919d7-103">Это диалоговое окно позволяет создать полнотекстовый индекс для полнотекстового поиска по столбцам, содержащим текстовые данные, в таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="919d7-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="919d7-104">Полнотекстовый индекс зависит от обычного индекса, поэтому необходимо сначала создать его.</span><span class="sxs-lookup"><span data-stu-id="919d7-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="919d7-105">Обычный индекс должен быть создан для одного столбца со значениями, отличными от NULL; лучше выбрать столбец с небольшими значениями, чем столбец с большими значениями.</span><span class="sxs-lookup"><span data-stu-id="919d7-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="919d7-106">Чтобы создать полнотекстовый индекс, необходимо сначала создать полнотекстовый каталог для базы данных, используя внешнее средство, например среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или программу Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="919d7-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="919d7-107">Функциональность полнотекстового индекса доступна не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="919d7-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="919d7-108">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="919d7-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="919d7-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="919d7-109">Options</span></span>  
 <span data-ttu-id="919d7-110">**Выбранный полнотекстовый индекс**</span><span class="sxs-lookup"><span data-stu-id="919d7-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="919d7-111">Отображает существующие полнотекстовые индексы.</span><span class="sxs-lookup"><span data-stu-id="919d7-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="919d7-112">Выберите индекс, чтобы отобразить его свойства в сетке, которая находится справа.</span><span class="sxs-lookup"><span data-stu-id="919d7-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="919d7-113">Если этот список пустой, для таблицы не определено ни одной полнотекстовой связи.</span><span class="sxs-lookup"><span data-stu-id="919d7-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="919d7-114">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="919d7-114">**Add**</span></span>  
 <span data-ttu-id="919d7-115">Создать полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="919d7-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="919d7-116">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="919d7-116">**Delete**</span></span>  
 <span data-ttu-id="919d7-117">Удаляет полнотекстовый индекс, выбранный из списка **Выбранный полнотекстовый индекс** .</span><span class="sxs-lookup"><span data-stu-id="919d7-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="919d7-118">**Общая категория**</span><span class="sxs-lookup"><span data-stu-id="919d7-118">**General Category**</span></span>  
 <span data-ttu-id="919d7-119">При развертывании показывает **Столбцы** и **Имя полнотекстового каталога**.</span><span class="sxs-lookup"><span data-stu-id="919d7-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="919d7-120">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="919d7-120">**Columns**</span></span>  
 <span data-ttu-id="919d7-121">Отображает список имен столбцов с разделителями-запятыми, по которым может быть осуществлен полнотекстовый поиск.</span><span class="sxs-lookup"><span data-stu-id="919d7-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="919d7-122">Чтобы увидеть полный список, нажмите кнопку с многоточием ( **…** ), которая находится слева от поля свойства.</span><span class="sxs-lookup"><span data-stu-id="919d7-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="919d7-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="919d7-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="919d7-124">Отображает имя полнотекстового каталога, в котором хранится полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="919d7-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="919d7-125">Чтобы сохранить индекс в другой каталог, щелкните имя каталога и выберите другой из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="919d7-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="919d7-126">Предварительно каталог должен быть создан при помощи внешнего инструмента, такого, как среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или программа Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="919d7-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="919d7-127">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="919d7-127">**Identity Category**</span></span>  
 <span data-ttu-id="919d7-128">Когда она открыта, показывает поле имени для этого индекса.</span><span class="sxs-lookup"><span data-stu-id="919d7-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="919d7-129">**Название**</span><span class="sxs-lookup"><span data-stu-id="919d7-129">**Name**</span></span>  
 <span data-ttu-id="919d7-130">Отображает установленное системой имя для этого полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="919d7-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="919d7-131">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="919d7-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="919d7-132">При развертывании показывает свойства, определяющие выполнение индекса.</span><span class="sxs-lookup"><span data-stu-id="919d7-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="919d7-133">**Активно**</span><span class="sxs-lookup"><span data-stu-id="919d7-133">**Active**</span></span>  
 <span data-ttu-id="919d7-134">Указывает на возможность или невозможность выполнения полнотекстового поиска с использованием данного полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="919d7-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="919d7-135">**Настройка отслеживания изменений**</span><span class="sxs-lookup"><span data-stu-id="919d7-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="919d7-136">Описывает состояние отслеживания изменений для этого индекса: "Вручную", "Автоматически" или "Отключено".</span><span class="sxs-lookup"><span data-stu-id="919d7-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="919d7-137">**Сканирование завершено**</span><span class="sxs-lookup"><span data-stu-id="919d7-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="919d7-138">Показывает, было ли завершено последнее сканирование.</span><span class="sxs-lookup"><span data-stu-id="919d7-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="919d7-139">Если это свойство отображается как «Нет», сканирование выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="919d7-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="919d7-140">**Дата и время окончания текущего или последнего сканирования**</span><span class="sxs-lookup"><span data-stu-id="919d7-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="919d7-141">Отображаются дата и время завершения последнего сканирования.</span><span class="sxs-lookup"><span data-stu-id="919d7-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="919d7-142">**Ошибки в текущем или в последнем сканировании**</span><span class="sxs-lookup"><span data-stu-id="919d7-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="919d7-143">Отображает число ошибок в текущем или в последнем сканировании.</span><span class="sxs-lookup"><span data-stu-id="919d7-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="919d7-144">**Версия индекса**</span><span class="sxs-lookup"><span data-stu-id="919d7-144">**Index Version**</span></span>  
 <span data-ttu-id="919d7-145">Отображает версию схемы таблицы на момент начала сканирования.</span><span class="sxs-lookup"><span data-stu-id="919d7-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="919d7-146">**Строки в текущем или последнем сканировании**</span><span class="sxs-lookup"><span data-stu-id="919d7-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="919d7-147">Отображает число строк, обновленных во время текущего или последнего сканирования.</span><span class="sxs-lookup"><span data-stu-id="919d7-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="919d7-148">**Дата и время начала текущего или последнего сканирования**</span><span class="sxs-lookup"><span data-stu-id="919d7-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="919d7-149">Отображаются дата и время начала текущего или последнего сканирования.</span><span class="sxs-lookup"><span data-stu-id="919d7-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="919d7-150">**Временная метка для следующего сканирования**</span><span class="sxs-lookup"><span data-stu-id="919d7-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="919d7-151">Отображаются дата и время запуска следующего сканирования.</span><span class="sxs-lookup"><span data-stu-id="919d7-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="919d7-152">**Тип текущего или последнего сканирования**</span><span class="sxs-lookup"><span data-stu-id="919d7-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="919d7-153">Отображает тип текущего или последнего сканирования: "Полное", "Добавочное", "Обновление" или "Автоматическое распространение".</span><span class="sxs-lookup"><span data-stu-id="919d7-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="919d7-154">**Уникальное имя индекса**</span><span class="sxs-lookup"><span data-stu-id="919d7-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="919d7-155">Отображает список всех имен столбцов в этой базе данных, которые имеют уникальные индексы по одиночному столбцу.</span><span class="sxs-lookup"><span data-stu-id="919d7-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="919d7-156">Эти столбцы могут быть использованы для создания полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="919d7-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="919d7-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="919d7-157">See Also</span></span>  
 <span data-ttu-id="919d7-158">[Использование мастера полнотекстового индексирования](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="919d7-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="919d7-159">CREATE FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="919d7-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
