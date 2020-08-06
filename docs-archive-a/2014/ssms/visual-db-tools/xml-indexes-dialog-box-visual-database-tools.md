---
title: Диалоговое окно "XML-индексы" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665706"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="dac7f-102">Диалоговое окно «XML-индексы» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="dac7f-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="dac7f-103">Используйте диалоговое окно **XML-индексы** для создания индексов для столбцов с типом данных XML, которые не могут быть индексированы, используя диалоговое окно **Индексы/Ключи** .</span><span class="sxs-lookup"><span data-stu-id="dac7f-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="dac7f-104">Каждый XML-столбец может иметь более одного XML-индекса, но созданный первым (первичный) будет основным для остальных (вторичных).</span><span class="sxs-lookup"><span data-stu-id="dac7f-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="dac7f-105">Если первичный XML-индекс удален, вторичные индексы также будут удалены.</span><span class="sxs-lookup"><span data-stu-id="dac7f-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dac7f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dac7f-106">Options</span></span>  
 <span data-ttu-id="dac7f-107">**Выбранный XML-индекс**</span><span class="sxs-lookup"><span data-stu-id="dac7f-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="dac7f-108">Отображает список существующих XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="dac7f-108">Lists existing XML indexes.</span></span> <span data-ttu-id="dac7f-109">Выберите параметр, чтобы отобразить его свойства в сетке, которая находится справа.</span><span class="sxs-lookup"><span data-stu-id="dac7f-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="dac7f-110">Если этот список пустой, для таблицы не определено ни одного индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="dac7f-111">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="dac7f-111">**Add**</span></span>  
 <span data-ttu-id="dac7f-112">Создать новый XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="dac7f-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="dac7f-113">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="dac7f-113">**Delete**</span></span>  
 <span data-ttu-id="dac7f-114">Удаление XML-индекса, выбранного в списке **Выбранный XML-индекс** .</span><span class="sxs-lookup"><span data-stu-id="dac7f-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="dac7f-115">Если удаляется первичный XML-индекс, вы получите уведомление о том, что этим также удаляются все вторичные индексы, и можно далее продолжить либо отменить действие.</span><span class="sxs-lookup"><span data-stu-id="dac7f-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="dac7f-116">**Общая категория**</span><span class="sxs-lookup"><span data-stu-id="dac7f-116">**General Category**</span></span>  
 <span data-ttu-id="dac7f-117">Когда она открыта, показывает поля свойств для **Столбцы**, **Первичный**и **Тип**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="dac7f-118">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="dac7f-118">**Columns**</span></span>  
 <span data-ttu-id="dac7f-119">Указывает на то, что этот индекс отсортирован в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="dac7f-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="dac7f-120">**Первичный**</span><span class="sxs-lookup"><span data-stu-id="dac7f-120">**Is Primary**</span></span>  
 <span data-ttu-id="dac7f-121">Указывает, является ли индекс первичным.</span><span class="sxs-lookup"><span data-stu-id="dac7f-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="dac7f-122">Первый XML-индекс, созданный для столбца, будет основой для остальных.</span><span class="sxs-lookup"><span data-stu-id="dac7f-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="dac7f-123">**Первичное эталонное имя**</span><span class="sxs-lookup"><span data-stu-id="dac7f-123">**Primary reference name**</span></span>  
 <span data-ttu-id="dac7f-124">Показывает имя первичного индекса, если данный является вторичным индексом.</span><span class="sxs-lookup"><span data-stu-id="dac7f-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="dac7f-125">Доступно только для вторичных индексов.</span><span class="sxs-lookup"><span data-stu-id="dac7f-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="dac7f-126">**Вторичный тип**</span><span class="sxs-lookup"><span data-stu-id="dac7f-126">**Secondary type**</span></span>  
 <span data-ttu-id="dac7f-127">Показывает тип вторичного индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-127">Shows the type of secondary index.</span></span> <span data-ttu-id="dac7f-128">Доступно только для вторичных индексов.</span><span class="sxs-lookup"><span data-stu-id="dac7f-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="dac7f-129">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dac7f-129">**Type**</span></span>  
 <span data-ttu-id="dac7f-130">Указывает на то, что это XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="dac7f-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="dac7f-131">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="dac7f-131">**Identity Category**</span></span>  
 <span data-ttu-id="dac7f-132">При развертывании показывает поля свойств **Имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="dac7f-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="dac7f-133">**Название**</span><span class="sxs-lookup"><span data-stu-id="dac7f-133">**Name**</span></span>  
 <span data-ttu-id="dac7f-134">Отображает имя XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-134">Shows the name of the XML index.</span></span> <span data-ttu-id="dac7f-135">Если создается новый индекс, ему присваивается имя по умолчанию, в зависимости от таблицы, отображаемой в окне конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="dac7f-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="dac7f-136">Имя можно изменить в любой момент.</span><span class="sxs-lookup"><span data-stu-id="dac7f-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="dac7f-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dac7f-137">**Description**</span></span>  
 <span data-ttu-id="dac7f-138">Создание описания индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-138">Describe the index.</span></span> <span data-ttu-id="dac7f-139">Чтобы ввести более подробное описание, нажмите кнопку **Описание**, а затем — кнопку с многоточием ( **...** ) справа от поля свойства.</span><span class="sxs-lookup"><span data-stu-id="dac7f-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="dac7f-140">При этом появится большее поле для записи текста.</span><span class="sxs-lookup"><span data-stu-id="dac7f-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="dac7f-141">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="dac7f-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="dac7f-142">Когда она открыта, показывает сведения о свойствах данного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="dac7f-143">**Характеристики заполнения**</span><span class="sxs-lookup"><span data-stu-id="dac7f-143">**Fill Specification**</span></span>  
 <span data-ttu-id="dac7f-144">В развернутом состоянии отображает сведения о параметрах **Коэффициент заполнения** и **Разредить индекс**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="dac7f-145">**Коэффициент заполнения**</span><span class="sxs-lookup"><span data-stu-id="dac7f-145">**Fill Factor**</span></span>  
 <span data-ttu-id="dac7f-146">Укажите, какой процент индексной страницы может заполнить система.</span><span class="sxs-lookup"><span data-stu-id="dac7f-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="dac7f-147">Как только страница заполнена, система должна разбить страницу, если добавлены новые данные, что снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="dac7f-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="dac7f-148">Значение, равное 100, означает, что страница будет заполнена; в этом случае требуется меньше всего объема пространства для хранения, но также будет наименее эффективно.</span><span class="sxs-lookup"><span data-stu-id="dac7f-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="dac7f-149">Данное значение должно использоваться только в том случае, если данные не будут изменяться: например в таблице, предназначенной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="dac7f-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="dac7f-150">Меньшее значение оставляет больше пустого пространства на страницах данных, что снижает необходимость разбиения страницы данных с ростом индексов.</span><span class="sxs-lookup"><span data-stu-id="dac7f-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="dac7f-151">Однако это потребует больше пространства для хранения.</span><span class="sxs-lookup"><span data-stu-id="dac7f-151">However, it requires more storage space.</span></span> <span data-ttu-id="dac7f-152">Этот параметр более необходим в случае, если данные в таблице будут меняться.</span><span class="sxs-lookup"><span data-stu-id="dac7f-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="dac7f-153">**Разредить индекс**</span><span class="sxs-lookup"><span data-stu-id="dac7f-153">**Pad Index**</span></span>  
 <span data-ttu-id="dac7f-154">Устанавливает для страниц в данном индексе такой же процент пустого пространства (заполнения), который указан в поле **Коэффициент заполнения**.</span><span class="sxs-lookup"><span data-stu-id="dac7f-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="dac7f-155">**Отключен**</span><span class="sxs-lookup"><span data-stu-id="dac7f-155">**Is Disabled**</span></span>  
 <span data-ttu-id="dac7f-156">Указывает, активирован ли данный индекс.</span><span class="sxs-lookup"><span data-stu-id="dac7f-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="dac7f-157">Отключенные индексы не поддерживают поиск и не обновляются, когда в таблицу добавляются новые элементы.</span><span class="sxs-lookup"><span data-stu-id="dac7f-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="dac7f-158">Можно улучшить производительность массовой вставки и обновлений, отключив индексы.</span><span class="sxs-lookup"><span data-stu-id="dac7f-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="dac7f-159">**Разрешить блокировку страниц**</span><span class="sxs-lookup"><span data-stu-id="dac7f-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="dac7f-160">Укажите, разрешены ли блокировки на уровне страниц для этого индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="dac7f-161">Разрешение или запрещение блокировок на уровне страниц влияет на производительность базы данных.</span><span class="sxs-lookup"><span data-stu-id="dac7f-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="dac7f-162">**Пересчитать статистику**</span><span class="sxs-lookup"><span data-stu-id="dac7f-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="dac7f-163">Вычисление новых статистических данных после создания индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="dac7f-164">Повторное вычисление статистических данных замедляет построение индексов, но обычно улучшает производительность выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="dac7f-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="dac7f-165">**Разрешить блокировку строк**</span><span class="sxs-lookup"><span data-stu-id="dac7f-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="dac7f-166">Укажите, разрешены ли блокировки на уровне строк для этого индекса.</span><span class="sxs-lookup"><span data-stu-id="dac7f-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="dac7f-167">Разрешение или запрещение блокировок на уровне строк влияет на производительность базы данных.</span><span class="sxs-lookup"><span data-stu-id="dac7f-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac7f-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="dac7f-168">See Also</span></span>  
 [<span data-ttu-id="dac7f-169">Создание XML-индексов</span><span class="sxs-lookup"><span data-stu-id="dac7f-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
