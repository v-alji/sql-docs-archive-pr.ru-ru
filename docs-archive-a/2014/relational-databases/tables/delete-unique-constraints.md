---
title: Удаление ограничения уникальности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665919"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="f3903-102">Удаление ограничений уникальности</span><span class="sxs-lookup"><span data-stu-id="f3903-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="f3903-103">Удалить ограничение уникальности в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3903-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f3903-104">Удаление ограничения уникальности приводит к удалению требования уникальности значений, вводимых в столбцы или в сочетание столбцов, указанных в выражении ограничения, а также к удалению соответствующего уникального индекса.</span><span class="sxs-lookup"><span data-stu-id="f3903-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="f3903-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f3903-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3903-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f3903-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3903-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f3903-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3903-108">**Удаление ограничения уникальности с использованием:**</span><span class="sxs-lookup"><span data-stu-id="f3903-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="f3903-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3903-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3903-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3903-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3903-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f3903-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3903-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="f3903-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3903-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="f3903-113">Permissions</span></span>  
 <span data-ttu-id="f3903-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="f3903-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3903-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3903-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="f3903-116">Удаление ограничения уникальности в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="f3903-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="f3903-117">В обозревателе объектов разверните таблицу, содержащую ограничение уникальности, а затем разверните узел **Ограничения**.</span><span class="sxs-lookup"><span data-stu-id="f3903-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="f3903-118">Щелкните ключ правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3903-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="f3903-119">В диалоговом окне **Удаление объекта** убедитесь в том, что выбран правильный ключ, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3903-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="f3903-120">Удаление ограничения уникальности с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="f3903-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="f3903-121">В **Обозревателе объектов**щелкните таблицу с ограничением уникальности правой кнопкой мыши и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="f3903-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="f3903-122">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="f3903-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="f3903-123">В диалоговом окне **Индексы и ключи** выберите уникальный ключ в списке **Выбранный первичный или уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="f3903-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="f3903-124">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3903-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="f3903-125">В меню **Файл** выберите команду **Сохранить** _имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="f3903-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3903-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3903-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="f3903-127">Удаление ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="f3903-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="f3903-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3903-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3903-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f3903-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3903-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3903-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="f3903-131">Дополнительные сведения см. в статьях [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) и [sys.objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3903-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
