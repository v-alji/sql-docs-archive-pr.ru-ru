---
title: Изменение связей по внешнему ключу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655554"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="6b461-102">Изменение связей по внешнему ключу</span><span class="sxs-lookup"><span data-stu-id="6b461-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="6b461-103">Изменить сторону внешнего ключа связи в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b461-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6b461-104">При изменении внешнего ключа таблицы изменяются столбцы, связанные со столбцами таблицы первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="6b461-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="6b461-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6b461-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6b461-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6b461-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6b461-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6b461-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6b461-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6b461-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6b461-109">**Изменение внешнего ключа с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="6b461-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="6b461-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b461-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6b461-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b461-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6b461-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6b461-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6b461-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6b461-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6b461-114">Тип данных и размер нового внешнего ключевого столбца должны соответствовать типу данных и размеру связанного с ним первичного ключевого столбца со следующими исключениями.</span><span class="sxs-lookup"><span data-stu-id="6b461-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="6b461-115">Столбец типа `char` или `sysname` можно связать со столбцом типа `varchar`.</span><span class="sxs-lookup"><span data-stu-id="6b461-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="6b461-116">Столбец типа `binary` можно связать со столбцом типа `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="6b461-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="6b461-117">Псевдоним типа данных можно связать со своим базовым типом.</span><span class="sxs-lookup"><span data-stu-id="6b461-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6b461-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="6b461-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6b461-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="6b461-119">Permissions</span></span>  
 <span data-ttu-id="6b461-120">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="6b461-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6b461-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b461-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="6b461-122">Изменение внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="6b461-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="6b461-123">Разверните в **обозревателе объектов**таблицу с внешним ключом, а затем разверните **Ключи**.</span><span class="sxs-lookup"><span data-stu-id="6b461-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="6b461-124">Щелкните правой кнопкой мыши внешний ключ, который нужно изменить, и выберите пункт **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6b461-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="6b461-125">В диалоговом окне **Связи внешних ключей** можно внести следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="6b461-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="6b461-126">**Выбранные связи**</span><span class="sxs-lookup"><span data-stu-id="6b461-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="6b461-127">Выводит список существующих связей.</span><span class="sxs-lookup"><span data-stu-id="6b461-127">Lists existing relationships.</span></span> <span data-ttu-id="6b461-128">Выберите связь, чтобы ее свойства отобразились в сетке справа.</span><span class="sxs-lookup"><span data-stu-id="6b461-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="6b461-129">Если этот список пуст, то для этой таблицы не было определено ни одной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="6b461-130">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="6b461-130">**Add**</span></span>  
     <span data-ttu-id="6b461-131">Создает новую связь.</span><span class="sxs-lookup"><span data-stu-id="6b461-131">Create a new relationship.</span></span> <span data-ttu-id="6b461-132">**Спецификации таблиц и столбцов** должны быть заданы, иначе связь будет недопустима.</span><span class="sxs-lookup"><span data-stu-id="6b461-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="6b461-133">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="6b461-133">**Delete**</span></span>  
     <span data-ttu-id="6b461-134">Удаляет связь, выбранную в списке **Выбранные связи** .</span><span class="sxs-lookup"><span data-stu-id="6b461-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="6b461-135">Чтобы отменить добавление связи, удалите эту связь, нажав данную кнопку.</span><span class="sxs-lookup"><span data-stu-id="6b461-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="6b461-136">**Общая категория**</span><span class="sxs-lookup"><span data-stu-id="6b461-136">**General Category**</span></span>  
     <span data-ttu-id="6b461-137">Разверните, чтобы увидеть категории **Проверить существующие данные при создании или повторном включении** и **Спецификации таблиц и столбцов**.</span><span class="sxs-lookup"><span data-stu-id="6b461-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="6b461-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="6b461-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="6b461-139">Проверяет все существующие данные в таблице перед созданием или возобновлением ограничения относительно этого ограничения.</span><span class="sxs-lookup"><span data-stu-id="6b461-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="6b461-140">**Категория спецификации таблиц и столбцов**</span><span class="sxs-lookup"><span data-stu-id="6b461-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="6b461-141">Разверните, чтобы увидеть, какие столбцы, из каких таблиц действуют как внешний и первичный (или уникальный) ключ в данной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="6b461-142">Для изменения или задания этих значений нажмите кнопку с многоточием ( **...** ) справа от поля свойства.</span><span class="sxs-lookup"><span data-stu-id="6b461-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="6b461-143">**Базовая таблица внешнего ключа**</span><span class="sxs-lookup"><span data-stu-id="6b461-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="6b461-144">Показывает, какая таблица содержит столбец, действующий как внешний ключ в выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="6b461-145">**Внешние ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="6b461-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="6b461-146">Показывает, какой столбец действует как внешний ключ в выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="6b461-147">**Базовая таблица первичного или уникального ключа**</span><span class="sxs-lookup"><span data-stu-id="6b461-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="6b461-148">Показывает, какая таблица содержит столбец, действующий как первичный (или уникальный) ключ в выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="6b461-149">**Первичные или уникальные ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="6b461-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="6b461-150">Показывает, какой столбец действует как первичный (или уникальный) ключ в выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="6b461-151">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="6b461-151">**Identity Category**</span></span>  
     <span data-ttu-id="6b461-152">Разверните, чтобы увидеть поля свойств **Имя** и **Описание**.</span><span class="sxs-lookup"><span data-stu-id="6b461-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="6b461-153">**Название**</span><span class="sxs-lookup"><span data-stu-id="6b461-153">**Name**</span></span>  
     <span data-ttu-id="6b461-154">Показывает имя связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-154">Shows the name of the relationship.</span></span> <span data-ttu-id="6b461-155">Если создается новая связь, ей присваивается имя по умолчанию в зависимости от таблицы, отображаемой в активном окне в **Конструкторе таблиц**.</span><span class="sxs-lookup"><span data-stu-id="6b461-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="6b461-156">Имя можно изменить в любой момент.</span><span class="sxs-lookup"><span data-stu-id="6b461-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="6b461-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6b461-157">**Description**</span></span>  
     <span data-ttu-id="6b461-158">Описывает связь.</span><span class="sxs-lookup"><span data-stu-id="6b461-158">Describe the relationship.</span></span> <span data-ttu-id="6b461-159">Чтобы ввести более подробное описание, щелкните **Описание** и нажмите кнопку с многоточием **(...)** справа от поля свойства.</span><span class="sxs-lookup"><span data-stu-id="6b461-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="6b461-160">При этом появится большее поле для записи текста.</span><span class="sxs-lookup"><span data-stu-id="6b461-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="6b461-161">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="6b461-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="6b461-162">Разверните, чтобы увидеть данные для категорий **Проверка существующих данных при создании и возобновлении** и **Включить использование для репликации**.</span><span class="sxs-lookup"><span data-stu-id="6b461-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="6b461-163">**Принудительное применение для репликации**</span><span class="sxs-lookup"><span data-stu-id="6b461-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="6b461-164">Показывает, использовать ли данное ограничение, когда агент репликации выполняет в таблице вставку, изменение или удаление.</span><span class="sxs-lookup"><span data-stu-id="6b461-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="6b461-165">**Принудительное использование ограничения внешнего ключа**</span><span class="sxs-lookup"><span data-stu-id="6b461-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="6b461-166">Укажите, допустимы ли изменения данных столбцов связи, если при этом нарушится целостность связи внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="6b461-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="6b461-167">Выберите **Да** , если нужно запретить такие изменения, и **Нет** , если нужно разрешить их.</span><span class="sxs-lookup"><span data-stu-id="6b461-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="6b461-168">**Категория спецификаций INSERT и UPDATE**</span><span class="sxs-lookup"><span data-stu-id="6b461-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="6b461-169">Разверните, чтобы увидеть сведения о **Правиле удаления** и **Правиле обновления** связи.</span><span class="sxs-lookup"><span data-stu-id="6b461-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="6b461-170">**Правиле удаления**</span><span class="sxs-lookup"><span data-stu-id="6b461-170">**Delete Rule**</span></span>  
     <span data-ttu-id="6b461-171">Укажите, что произойдет при попытке пользователя удалить строку с данными, участвующую в связи внешнего ключа:</span><span class="sxs-lookup"><span data-stu-id="6b461-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="6b461-172">**Нет действий.** Сообщение об ошибке информирует пользователя, что удаление недопустимо, и инструкция DELETE откатывается.</span><span class="sxs-lookup"><span data-stu-id="6b461-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="6b461-173">**Каскад.** Удаляет все строки, содержащие данные, участвующие в связи внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="6b461-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="6b461-174">Не следует использовать параметр CASCADE, если таблица будет включена в публикацию слиянием, в которой используются логические записи.</span><span class="sxs-lookup"><span data-stu-id="6b461-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="6b461-175">**Присвоить NULL** . Задает значение, равное NULL, если все внешние ключевые столбцы в таблице могут содержать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="6b461-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="6b461-176">**Присвоить значение по умолчанию** . Задает значение по умолчанию, определенное для данного столбца, если все внешние ключевые столбцы в таблице имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b461-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="6b461-177">**Правиле обновления**</span><span class="sxs-lookup"><span data-stu-id="6b461-177">**Update Rule**</span></span>  
     <span data-ttu-id="6b461-178">Укажите, что произойдет при попытке пользователя обновить строку с данными, участвующую в связи внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="6b461-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="6b461-179">**Нет действий.** Сообщение об ошибке информирует пользователя, что обновление недопустимо, и инструкция UPDATE откатывается.</span><span class="sxs-lookup"><span data-stu-id="6b461-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="6b461-180">**Каскад.** Обновляет все строки, содержащие данные, участвующие в связи внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="6b461-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="6b461-181">Не следует использовать параметр CASCADE, если таблица будет включена в публикацию слиянием, в которой используются логические записи.</span><span class="sxs-lookup"><span data-stu-id="6b461-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="6b461-182">**Присвоить NULL** . Задает значение, равное NULL, если все внешние ключевые столбцы в таблице могут содержать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="6b461-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="6b461-183">**Присвоить значение по умолчанию.** Задает значение по умолчанию, определенное для данного столбца, если все внешние ключевые столбцы в таблице имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b461-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="6b461-184">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="6b461-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6b461-185">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b461-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="6b461-186">**Изменение внешнего ключа**</span><span class="sxs-lookup"><span data-stu-id="6b461-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="6b461-187">Чтобы изменить ограничение FOREIGN KEY с помощью Transact-SQL, сначала необходимо удалить существующее ограничение FOREIGN KEY, а затем повторно создать его с новым определением.</span><span class="sxs-lookup"><span data-stu-id="6b461-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="6b461-188">Дополнительные сведения см. в разделах [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) и [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6b461-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
