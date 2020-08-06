---
title: Свойства таблицы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735777"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="29764-102">Свойства таблицы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="29764-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="29764-103">Эти свойства отображаются в окне «Свойства», при щелчке правой кнопкой мыши в конструкторе таблиц и выборе пункта «Свойства».</span><span class="sxs-lookup"><span data-stu-id="29764-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="29764-104">Если иное не указано, можно редактировать эти свойства в окне «Свойства», выбрав соответствующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="29764-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29764-105">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="29764-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="29764-106">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="29764-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="29764-107">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="29764-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="29764-108">Показать свойства таблицы в конструкторе таблицы</span><span class="sxs-lookup"><span data-stu-id="29764-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29764-109">Свойства в данном разделе сгруппированы по категориям, а не по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="29764-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="29764-110">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="29764-110">**Identity Category**</span></span>  
 <span data-ttu-id="29764-111">Разворачивается, чтобы отобразить свойства для параметров **Имя**, **Описание**и **Схема**.</span><span class="sxs-lookup"><span data-stu-id="29764-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="29764-112">**Название**</span><span class="sxs-lookup"><span data-stu-id="29764-112">**Name**</span></span>  
 <span data-ttu-id="29764-113">Отображает имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="29764-113">Displays the name of the table.</span></span> <span data-ttu-id="29764-114">Для изменения имени введите его в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="29764-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="29764-115">Если существующие запросы, представления, определенные пользователем функции, хранимые процедуры или программы ссылаются на таблицу, изменение имени таблицы сделает эти объекты недействительными.</span><span class="sxs-lookup"><span data-stu-id="29764-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="29764-116">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="29764-116">**Database Name**</span></span>  
 <span data-ttu-id="29764-117">Показывает имя источника данных выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="29764-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="29764-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="29764-118">**Description**</span></span>  
 <span data-ttu-id="29764-119">Показывает описание выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="29764-119">Shows a description of the selected table.</span></span> <span data-ttu-id="29764-120">Чтобы просмотреть или отредактировать описание целиком, щелкните его и затем нажмите кнопку с многоточием **(...)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="29764-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="29764-121">**Схема**</span><span class="sxs-lookup"><span data-stu-id="29764-121">**Schema**</span></span>  
 <span data-ttu-id="29764-122">Показывает имя схемы, которой принадлежит таблица</span><span class="sxs-lookup"><span data-stu-id="29764-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="29764-123">(применимо только к Microsoft SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="29764-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="29764-124">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="29764-124">**Server Name**</span></span>  
 <span data-ttu-id="29764-125">Показывает имя сервера для источника данных.</span><span class="sxs-lookup"><span data-stu-id="29764-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="29764-126">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="29764-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="29764-127">Разворачивается, чтобы показать свойства параметров **Столбец идентификаторов**, **Индексируемая**и **Реплицируемая**.</span><span class="sxs-lookup"><span data-stu-id="29764-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="29764-128">**Столбец идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="29764-128">**Identity Column**</span></span>  
 <span data-ttu-id="29764-129">Показывает столбец, используемый в качестве столбца идентификаторов таблицы.</span><span class="sxs-lookup"><span data-stu-id="29764-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="29764-130">Чтобы изменить столбец идентификаторов, выберите нужный столбец из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="29764-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="29764-131">Только столбцы с числовым типом данных будут показаны в списке.</span><span class="sxs-lookup"><span data-stu-id="29764-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="29764-132">**Индексируемый**</span><span class="sxs-lookup"><span data-stu-id="29764-132">**Is Indexable**</span></span>  
 <span data-ttu-id="29764-133">Показывает, подлежит ли таблица индексированию.</span><span class="sxs-lookup"><span data-stu-id="29764-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="29764-134">Если таблица не подлежит индексированию, это может быть потому, что данный пользователь не является владельцем таблицы, или потому, что таблица содержит столбцы с типами данных text, ntext или image.</span><span class="sxs-lookup"><span data-stu-id="29764-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="29764-135">**Реплицирован**</span><span class="sxs-lookup"><span data-stu-id="29764-135">**Is Replicated**</span></span>  
 <span data-ttu-id="29764-136">Показывает, выполняется ли репликация таблицы в другом местоположении.</span><span class="sxs-lookup"><span data-stu-id="29764-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="29764-137">**Категория спецификации регулярного пространства данных**</span><span class="sxs-lookup"><span data-stu-id="29764-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="29764-138">Разворачивается, чтобы показать свойства параметров **(Тип пространства данных)** , **Имя файловой группы или схемы секционирования**и **Список столбцов секционирования**.</span><span class="sxs-lookup"><span data-stu-id="29764-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="29764-139">**(Тип пространства данных)**</span><span class="sxs-lookup"><span data-stu-id="29764-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="29764-140">Показывает, хранится ли эта таблица с использованием файловой группы или схемы секционирования.</span><span class="sxs-lookup"><span data-stu-id="29764-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="29764-141">**Имя файловой группы или схемы секционирования**</span><span class="sxs-lookup"><span data-stu-id="29764-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="29764-142">Показывает имя файловой группы или схемы секционирования.</span><span class="sxs-lookup"><span data-stu-id="29764-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="29764-143">**Список столбцов секционирования**</span><span class="sxs-lookup"><span data-stu-id="29764-143">**Partition Column List**</span></span>  
 <span data-ttu-id="29764-144">Обеспечивает доступ к диалоговому окну **Список столбцов секционирования** .</span><span class="sxs-lookup"><span data-stu-id="29764-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="29764-145">**Столбец ROWGUID**</span><span class="sxs-lookup"><span data-stu-id="29764-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="29764-146">Показывает столбец, используемый Microsoft SQL Server в качестве столбца ROWGUID таблицы.</span><span class="sxs-lookup"><span data-stu-id="29764-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="29764-147">Чтобы изменить столбец ROWGUID, выберите нужный из раскрывающегося списка</span><span class="sxs-lookup"><span data-stu-id="29764-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="29764-148">(только в Microsoft SQL Server 7.0 или более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="29764-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="29764-149">**Файловая группа Text/Image**</span><span class="sxs-lookup"><span data-stu-id="29764-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="29764-150">Предоставляет раскрывающийся список, из которого можно выбрать файловую группу для столбцов с типами данных text или image.</span><span class="sxs-lookup"><span data-stu-id="29764-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="29764-151">Если таблица хранится с использованием схемы секционирования, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="29764-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29764-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="29764-152">See Also</span></span>  
 [<span data-ttu-id="29764-153">Проектирование таблиц (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="29764-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
