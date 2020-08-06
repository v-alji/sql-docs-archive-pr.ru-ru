---
title: Диалоговое окно "Проверочное ограничение" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654006"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="feff6-102">Диалоговое окно «Проверочное ограничение» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="feff6-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="feff6-103">Это диалоговое окно выводится, если в конструкторе таблиц щелкнуть правой кнопкой мыши сетку определения таблицы и выбрать пункт **Проверочные ограничения**.</span><span class="sxs-lookup"><span data-stu-id="feff6-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="feff6-104">Диалоговое окно содержит набор свойств для ограничений, отличных от ограничений уникальности, присоединенных к таблицам базы данных.</span><span class="sxs-lookup"><span data-stu-id="feff6-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="feff6-105">Свойства, применяемые к ограничениям уникальности, отображаются в диалоговом окне **Индексы/Ключи** .</span><span class="sxs-lookup"><span data-stu-id="feff6-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="feff6-106">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="feff6-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="feff6-107">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="feff6-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="feff6-108">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="feff6-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="feff6-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="feff6-109">Options</span></span>  
 <span data-ttu-id="feff6-110">**Выбранные проверочные ограничения**</span><span class="sxs-lookup"><span data-stu-id="feff6-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="feff6-111">Перечисляет имеющиеся проверочные ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-111">Lists available check constraints.</span></span> <span data-ttu-id="feff6-112">Для просмотра свойств ограничения выберите это ограничение в списке.</span><span class="sxs-lookup"><span data-stu-id="feff6-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="feff6-113">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="feff6-113">**Add**</span></span>  
 <span data-ttu-id="feff6-114">Создается новое ограничение для выбранной таблицы базы данных и предоставляется имя по умолчанию и другие значения для ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="feff6-115">Ограничение не будет действительным, пока не будет введено выражение для ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="feff6-116">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="feff6-116">**Delete**</span></span>  
 <span data-ttu-id="feff6-117">Удалить выбранное ограничение из таблицы.</span><span class="sxs-lookup"><span data-stu-id="feff6-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="feff6-118">Для отмены добавления проверочного ограничения используйте эту кнопку удаления ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="feff6-119">**Общая категория**</span><span class="sxs-lookup"><span data-stu-id="feff6-119">**General Category**</span></span>  
 <span data-ttu-id="feff6-120">Откройте для отображения поля свойства **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="feff6-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="feff6-121">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="feff6-121">**Expression**</span></span>  
 <span data-ttu-id="feff6-122">Отображается выражение для выбранного проверочного ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="feff6-123">При создании новых ограничений перед выходом из этого диалогового окна необходимо ввести выражение.</span><span class="sxs-lookup"><span data-stu-id="feff6-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="feff6-124">Можно также изменить имеющиеся проверочные ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="feff6-125">Дополнительные сведения см. в статье [Ограничения уникальности и проверочные ограничения](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="feff6-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="feff6-126">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="feff6-126">**Identity Category**</span></span>  
 <span data-ttu-id="feff6-127">Разверните для отображения свойств **Имя** и **Описание**.</span><span class="sxs-lookup"><span data-stu-id="feff6-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="feff6-128">**Название**</span><span class="sxs-lookup"><span data-stu-id="feff6-128">**Name**</span></span>  
 <span data-ttu-id="feff6-129">Отображает имя выбранного проверочного ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="feff6-130">Для изменения имени этого ограничения введите текст непосредственно в поле свойства.</span><span class="sxs-lookup"><span data-stu-id="feff6-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="feff6-131">**Описание**</span><span class="sxs-lookup"><span data-stu-id="feff6-131">**Description**</span></span>  
 <span data-ttu-id="feff6-132">Содержит описание проверочного ограничения.</span><span class="sxs-lookup"><span data-stu-id="feff6-132">Describing this check constraint.</span></span> <span data-ttu-id="feff6-133">Можно отредактировать описание прямо в этом поле либо нажать кнопку с многоточием ( **...** ), находящуюся справа от поля, и редактировать описание в диалоговом окне **Свойство описания**.</span><span class="sxs-lookup"><span data-stu-id="feff6-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="feff6-134">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="feff6-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="feff6-135">Разверните, чтобы просмотреть свойства для **Проверить существующие данные при создании или повторном включении**, **Применять для INSERT и UPDATE**и **Включить использование для репликации**.</span><span class="sxs-lookup"><span data-stu-id="feff6-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="feff6-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="feff6-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="feff6-137">Определяет, проверяются ли все уже существующие данные (данные, существовавшие в таблице до создания ограничения) на соответствие ограничению.</span><span class="sxs-lookup"><span data-stu-id="feff6-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="feff6-138">**Применять для INSERT и UPDATE**</span><span class="sxs-lookup"><span data-stu-id="feff6-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="feff6-139">Определяет, действует ли ограничение при вставке или изменении данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="feff6-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="feff6-140">**Принудительное применение для репликации**</span><span class="sxs-lookup"><span data-stu-id="feff6-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="feff6-141">Показывает, действует ли ограничение, когда агент репликации производит вставку или изменение в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="feff6-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feff6-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="feff6-142">See Also</span></span>  
 <span data-ttu-id="feff6-143">[Ограничения UNIQUE и проверочные ограничения](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="feff6-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="feff6-144">Диалоговое окно "индексы и ключи" &#40;визуальных инструментов для баз данных&#41;</span><span class="sxs-lookup"><span data-stu-id="feff6-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
