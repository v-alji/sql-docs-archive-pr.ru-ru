---
title: Вопросы управления издателями Oracle | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666498"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="9807e-102">Вопросы управления издателями Oracle</span><span class="sxs-lookup"><span data-stu-id="9807e-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="9807e-103">После завершения настройки издателя Oracle и установки механизмов отслеживания изменения репликаций администраторы систем баз данных Oracle могут использовать стандартные служебные программы Oracle и выполнять типичные задачи системного администратора.</span><span class="sxs-lookup"><span data-stu-id="9807e-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="9807e-104">Однако необходимо знать о влиянии некоторых административных задач на публикуемые данные.</span><span class="sxs-lookup"><span data-stu-id="9807e-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="9807e-105">За исключением удаления или изменения столбца, публикуемого для репликации, либо удаления или изменения любого объекта репликации, эти вопросы не относятся к публикациям моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="9807e-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="9807e-106">Импорт и загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9807e-106">Importing and loading data</span></span>  
 <span data-ttu-id="9807e-107">Триггеры используются для отслеживания изменений публикаций транзакций в Oracle.</span><span class="sxs-lookup"><span data-stu-id="9807e-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="9807e-108">Изменения опубликованных таблиц можно реплицировать на подписчики, только если триггеры репликации запускаются, когда происходит обновление, вставка или удаление.</span><span class="sxs-lookup"><span data-stu-id="9807e-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="9807e-109">В служебных программах Oracle Import и SQL\*Loader имеются параметры, которые влияют на запуск триггеров при вставке строк в реплицированные таблицы с помощью этих программ.</span><span class="sxs-lookup"><span data-stu-id="9807e-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="9807e-110">Служебная программа Oracle Import</span><span class="sxs-lookup"><span data-stu-id="9807e-110">Oracle Import</span></span>  
 <span data-ttu-id="9807e-111">С помощью программы Oracle Import можно присвоить параметру **ignore** значение 'y' или 'n' (по умолчанию 'n').</span><span class="sxs-lookup"><span data-stu-id="9807e-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="9807e-112">Если параметр **ignore** имеет значение 'n', таблица во время импорта удаляется и создается заново.</span><span class="sxs-lookup"><span data-stu-id="9807e-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="9807e-113">Таким образом удаляются триггеры репликации и отключается репликация.</span><span class="sxs-lookup"><span data-stu-id="9807e-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="9807e-114">Если параметр **ignore** имеет значение 'y', операция импорта попытается загрузить строки в существующую таблицу, что запускает триггеры репликации.</span><span class="sxs-lookup"><span data-stu-id="9807e-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="9807e-115">Поэтому при импорте реплицированной таблицы с помощью инструмента Import убедитесь, что параметру **ignore** присвоено значение 'y'.</span><span class="sxs-lookup"><span data-stu-id="9807e-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="9807e-116">Служебная программа SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="9807e-116">SQL\*Loader</span></span>  
 <span data-ttu-id="9807e-117">С помощью программы SQL\*Loader можно присвоить параметру **direct** значение true или false (по умолчанию — false).</span><span class="sxs-lookup"><span data-stu-id="9807e-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="9807e-118">Если параметр **direct** имеет значение 'false', строки вставляются с использованием обычных инструкций INSERT, что запускает триггеры репликации.</span><span class="sxs-lookup"><span data-stu-id="9807e-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="9807e-119">Если параметр **direct** имеет значение 'true', загрузка оптимизируется, а триггеры не запускаются.</span><span class="sxs-lookup"><span data-stu-id="9807e-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="9807e-120">Поэтому при загрузке реплицированной таблицы с помощью инструмента SQL\*Loader убедитесь, что параметру **direct** присвоено значение 'false'.</span><span class="sxs-lookup"><span data-stu-id="9807e-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="9807e-121">Внесение изменений в опубликованные объекты</span><span class="sxs-lookup"><span data-stu-id="9807e-121">Making changes to published objects</span></span>  
 <span data-ttu-id="9807e-122">Для следующих действий не требуются особые соображения:</span><span class="sxs-lookup"><span data-stu-id="9807e-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="9807e-123">Перестроение индексов в опубликованных таблицах.</span><span class="sxs-lookup"><span data-stu-id="9807e-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="9807e-124">Добавление пользовательских триггеров у опубликованную таблицу.</span><span class="sxs-lookup"><span data-stu-id="9807e-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="9807e-125">Следующее действие требует остановки всех операций в опубликованных таблицах:</span><span class="sxs-lookup"><span data-stu-id="9807e-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="9807e-126">Перемещение опубликованной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9807e-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="9807e-127">Для следующих действий требуется удалить публикацию, выполнить нужное действие, а затем заново создать эту публикацию:</span><span class="sxs-lookup"><span data-stu-id="9807e-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="9807e-128">Усечение опубликованной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9807e-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="9807e-129">Переименование опубликованной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9807e-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="9807e-130">Добавление столбца в опубликованную таблицу.</span><span class="sxs-lookup"><span data-stu-id="9807e-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="9807e-131">Удаление или изменение столбца, опубликованного для репликации.</span><span class="sxs-lookup"><span data-stu-id="9807e-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="9807e-132">Выполнение операций, не регистрируемых в журналах.</span><span class="sxs-lookup"><span data-stu-id="9807e-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="9807e-133">Удаление или изменение объектов репликации</span><span class="sxs-lookup"><span data-stu-id="9807e-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="9807e-134">Необходимо удалить и заново сконфигурировать издателя, если удаляются или изменяются любые таблицы отслеживания, триггеры, последовательности или хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="9807e-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="9807e-135">Неполный список этих объектов собран в статье [Объекты, создаваемые на издателе Oracle](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="9807e-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="9807e-136">Сведения об удалении и повторной настройке издателя см. в подразделе «Изменения, требующие повторной настройки издателя» раздела [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="9807e-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9807e-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="9807e-137">See Also</span></span>  
 <span data-ttu-id="9807e-138">[Настройка издателя Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="9807e-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="9807e-139">[Рекомендации по структуре и ограничения для издателей Oracle](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="9807e-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="9807e-140">Обзор публикации Oracle</span><span class="sxs-lookup"><span data-stu-id="9807e-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
