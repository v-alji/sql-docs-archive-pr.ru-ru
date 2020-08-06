---
title: Пошаговое руководство. Добавление и изменение диаграммы базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655510"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="dbfa1-102">Пошаговое руководство. Добавление и изменение диаграммы базы данных</span><span class="sxs-lookup"><span data-stu-id="dbfa1-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="dbfa1-103">Это пошаговое руководство показывает, как создавать и изменять диаграмму базы данных и производить изменения в базе данных с помощью компонента диаграмм базы данных.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="dbfa1-104">Рассматривается добавление таблиц в диаграммы, создание связей между таблицами, создание ограничений и индексов столбцов и изменение уровня сведений, видимых для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dbfa1-105">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="dbfa1-105">Prerequisites</span></span>  
 <span data-ttu-id="dbfa1-106">Для выполнения задач этого руководства необходимы:</span><span class="sxs-lookup"><span data-stu-id="dbfa1-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="dbfa1-107">Доступ к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с образцом базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbfa1-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="dbfa1-108">Учетная запись с правами владельца базы данных `dbo`</span><span class="sxs-lookup"><span data-stu-id="dbfa1-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbfa1-109">При попытке сделать изменения с использованием учетной записи, разрешения которой недостаточны для внесения изменений в таблицы, появляется сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="dbfa1-110">Создание диаграммы</span><span class="sxs-lookup"><span data-stu-id="dbfa1-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="dbfa1-111">Для создания новой диаграммы базы данных</span><span class="sxs-lookup"><span data-stu-id="dbfa1-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="dbfa1-112">В меню **Вид** выберите **Обозреватель объектов**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="dbfa1-113">Откройте узел «Базы данных», а затем узел [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="dbfa1-114">Щелкните правой кнопкой узел "Диаграммы баз данных" и выберите **Создать диаграмму базы данных**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="dbfa1-115">Если в базе данных отсутствуют объекты, необходимые для создания диаграмм, появляется следующее сообщение: **Для этой базы данных отсутствует один или несколько объектов поддержки, необходимых для использования функции построения диаграмм баз данных. Создать их?**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="dbfa1-116">выберите **Yes** (Да).</span><span class="sxs-lookup"><span data-stu-id="dbfa1-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="dbfa1-117">Отображается диалоговое окно **Добавление таблицы** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="dbfa1-118">Выберите таблицы **AddressType (Person)** и **Address (Person)** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="dbfa1-119">В диаграмму будут добавлены две таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="dbfa1-120">Закройте диалоговое окно **Добавление таблицы** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="dbfa1-121">Просмотр данных другого столбца</span><span class="sxs-lookup"><span data-stu-id="dbfa1-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="dbfa1-122">Щелкните правой кнопкой мыши таблицу `Address` .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-122">Right-click the `Address` table.</span></span> <span data-ttu-id="dbfa1-123">В контекстном меню выберите **Вид таблицы**и выберите **Стандартный**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="dbfa1-124">Сетка таблицы отображает три столбца: **Имя столбца**, **Тип данных**и **Разрешить значения NULL**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="dbfa1-125">Щелкните правой кнопкой мыши таблицу `Address` , выберите **Вид таблицы** и **Ключи**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="dbfa1-126">Сетка таблицы отображает один столбец, содержащий имена столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="dbfa1-127">Появятся только столбцы, которые участвуют в индексах.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="dbfa1-128">Создание новых таблиц</span><span class="sxs-lookup"><span data-stu-id="dbfa1-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="dbfa1-129">Создание таблиц в конструкторе диаграмм</span><span class="sxs-lookup"><span data-stu-id="dbfa1-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="dbfa1-130">Щелкните правой кнопкой мыши конструктор диаграмм вне существующих таблиц и выберите **Создать таблицу**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="dbfa1-131">В диалоговом окне **Выбор имени** нажмите кнопку **ОК** , чтобы принять имя по умолчанию `Table1` .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="dbfa1-132">Появится новая сетка таблицы с тремя столбцами: **Имя столбца**, **Тип данных**и **Разрешить значения NULL**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="dbfa1-133">Добавьте следующие сведения в `Table1` :</span><span class="sxs-lookup"><span data-stu-id="dbfa1-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="dbfa1-134">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-134">**Column Name**</span></span>|<span data-ttu-id="dbfa1-135">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-135">**Data Type**</span></span>|<span data-ttu-id="dbfa1-136">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="dbfa1-137">checked</span><span class="sxs-lookup"><span data-stu-id="dbfa1-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="dbfa1-138">checked</span><span class="sxs-lookup"><span data-stu-id="dbfa1-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="dbfa1-139">включен</span><span class="sxs-lookup"><span data-stu-id="dbfa1-139">checked</span></span>|  
  
4.  <span data-ttu-id="dbfa1-140">Щелкните правой кнопкой мыши `T1col1` и выберите команду **Задать первичный ключ**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="dbfa1-141">Рядом с именем столбца появится значок ключа.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="dbfa1-142">В меню **Файл** выберите пункт **Сохранить Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="dbfa1-143">В диалоговом окне **Выбор имени** нажмите кнопку **ОК** , чтобы принять имя по умолчанию `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="dbfa1-144">Откроется диалоговое окно **Сохранить** с сообщением, что `Table1` будет сохранена в базу данных.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="dbfa1-145">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="dbfa1-146">Изменение структуры таблицы</span><span class="sxs-lookup"><span data-stu-id="dbfa1-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="dbfa1-147">В конструкторе диаграмм можно добавить проверочные ограничения и создать связи между таблицами.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="dbfa1-148">Создание проверочных ограничений</span><span class="sxs-lookup"><span data-stu-id="dbfa1-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="dbfa1-149">В `Table1`щелкните правой кнопкой мыши строку `T1col3` и выберите **Проверочные ограничения**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="dbfa1-150">Будет открыто диалоговое окно **Проверочные ограничения** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="dbfa1-151">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="dbfa1-152">В списке **Выбранные проверочные ограничения** появится новое проверочное ограничение с именем по умолчанию `CK_Table1`.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="dbfa1-153">Выберите строку **Выражение** в сетке и нажмите кнопку с многоточием.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="dbfa1-154">Будет открыто диалоговое окно **Выражение проверочного ограничения**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="dbfa1-155">Введите `T1col3 > 5` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="dbfa1-156">`Table1` содержит теперь ограничение, согласно которому все значения столбца `T1col3` должны быть больше 5.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="dbfa1-157">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="dbfa1-158">Создание связей между таблицами</span><span class="sxs-lookup"><span data-stu-id="dbfa1-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="dbfa1-159">В конструкторе диаграмм создайте новую таблицу `Table2` со следующими столбцами.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="dbfa1-160">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-160">**Column Name**</span></span>|<span data-ttu-id="dbfa1-161">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-161">**Data Type**</span></span>|<span data-ttu-id="dbfa1-162">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="dbfa1-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="dbfa1-163">не включен</span><span class="sxs-lookup"><span data-stu-id="dbfa1-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="dbfa1-164">checked</span><span class="sxs-lookup"><span data-stu-id="dbfa1-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="dbfa1-165">checked</span><span class="sxs-lookup"><span data-stu-id="dbfa1-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbfa1-166">Столбцы на стороне первичного ключа связи внешнего ключа должны быть включены в первичный ключ или в ограничение уникальности.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="dbfa1-167">Перетащите `T2col1` к `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="dbfa1-168">Отображаются два диалоговых окна: **Связь по внешнему ключу** на заднем плане и **Таблицы и столбцы** на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="dbfa1-169">Нажмите кнопку **OK** , чтобы сохранить новую связь.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="dbfa1-170">Снова нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="dbfa1-171">Создание индексов</span><span class="sxs-lookup"><span data-stu-id="dbfa1-171">Creating Indexes</span></span>  
 <span data-ttu-id="dbfa1-172">Индексы можно создавать на большинстве типов данных, включая XML.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="dbfa1-173">Создание стандартного индекса</span><span class="sxs-lookup"><span data-stu-id="dbfa1-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="dbfa1-174">Щелкните правой кнопкой мыши `Table1` и выберите **Индексы/Ключи**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="dbfa1-175">Открывается диалоговое окно **Индексы/Ключи** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="dbfa1-176">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="dbfa1-177">Новый индекс появится в списке **Выбранный первичный (уникальный) ключ или индекс** с именем по умолчанию, подобным `IX_Table1`.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="dbfa1-178">Выберите строку **Столбцы** и нажмите кнопку с многоточием.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="dbfa1-179">Отображается диалоговое окно **Столбцы индекса** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="dbfa1-180">Щелкните стрелку раскрывающегося списка под полем **Имя столбца** и выберите `T1col2`.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbfa1-181">В индекс можно добавить дополнительные столбцы, выбрав ячейку под `T1col2` и выбрав другое имя столбца.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="dbfa1-182">Нажмите кнопку **ОК** для сохранения этого индекса.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="dbfa1-183">Нажмите кнопку **Закрыть** в диалоговом окне **Индексы/Ключи** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="dbfa1-184">Создание XML-индекса</span><span class="sxs-lookup"><span data-stu-id="dbfa1-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="dbfa1-185">Щелкните правой кнопкой мыши `T2col1` и выберите команду **Задать первичный ключ**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbfa1-186">Чтобы добавить XML-индекс, необходимо, чтобы другой столбец в таблице был установлен в качестве кластеризованного первичного ключа таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="dbfa1-187">Щелкните правой кнопкой мыши строку `T2col3` в `Table2` и выберите пункт **XML-индексы**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="dbfa1-188">Отображается диалоговое окно **XML-индексы** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="dbfa1-189">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="dbfa1-190">В список **Выбранный XML-индекс** будет добавлен XML-индекс со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="dbfa1-191">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbfa1-192">XML-индексы создаются для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-192">XML indexes are created per-column.</span></span> <span data-ttu-id="dbfa1-193">Первый индекс XML-столбца является первичным, все дополнительные XML-индексы являются вторичными.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="dbfa1-194">Сохранение диаграммы</span><span class="sxs-lookup"><span data-stu-id="dbfa1-194">Saving the Diagram</span></span>  
 <span data-ttu-id="dbfa1-195">Все изменения в диаграмме не будут отправлены в базу данных до тех пор, пока диаграмма не будет сохранена.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="dbfa1-196">В случае возникновения проблем и конфликтов появляется диалоговое окно, содержащее дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="dbfa1-197">Сохранение диаграммы базы данных</span><span class="sxs-lookup"><span data-stu-id="dbfa1-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="dbfa1-198">В меню **Файл** выберите команду **Сохранить Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="dbfa1-199">Отображается диалоговое окно **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="dbfa1-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="dbfa1-200">Если установлен флажок **Предупреждать о затронутых таблицах** , перечисляются сведения о новых и измененных таблицах.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="dbfa1-201">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="dbfa1-202">В случае ошибок открывается диалоговое окно **Уведомления после сохранения** , содержащее ошибки и их причины.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="dbfa1-203">Исправьте ошибки и сохраните диаграмму снова.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dbfa1-204">Next Steps</span><span class="sxs-lookup"><span data-stu-id="dbfa1-204">Next Steps</span></span>  
 <span data-ttu-id="dbfa1-205">Это базовая диаграмма, содержащая только две существующие и две новые таблицы, но она иллюстрирует возможность создания схемы существующей базы данных или визуального создания новой схемы.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="dbfa1-206">Для лучшего изучения можно предложить следующее:</span><span class="sxs-lookup"><span data-stu-id="dbfa1-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="dbfa1-207">создать новые диаграммы, содержащие группы связанных таблиц;</span><span class="sxs-lookup"><span data-stu-id="dbfa1-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="dbfa1-208">настроить объем данных, отображаемых в каждой таблице;</span><span class="sxs-lookup"><span data-stu-id="dbfa1-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="dbfa1-209">изменить разметку и добавить заметки;</span><span class="sxs-lookup"><span data-stu-id="dbfa1-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="dbfa1-210">скопировать диаграмму в битовую карту.</span><span class="sxs-lookup"><span data-stu-id="dbfa1-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbfa1-211">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbfa1-211">See Also</span></span>  
 <span data-ttu-id="dbfa1-212">[Настройка объема сведений, отображаемых на диаграммах &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="dbfa1-213">[Настройка конструктора диаграмм баз данных &#40;визуальных инструментов для баз данных&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="dbfa1-214">[Добавление таблиц в диаграммы &#40;визуальных инструментов для баз данных&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="dbfa1-215">[Создание связей между таблицами на схеме &#40;визуальных инструментов для баз данных&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="dbfa1-216">[Создание XML-индексов](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="dbfa1-217">[Копирование изображения диаграммы базы данных в буфер обмена &#40;визуальные инструменты для баз данных&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dbfa1-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="dbfa1-218">Работа с макетом диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="dbfa1-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
