---
title: Удаление таблиц (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738159"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="fe027-102">Удаление таблиц (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="fe027-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="fe027-103">Удалить таблицу из базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe027-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fe027-104">Каждое удаление таблицы следует тщательно планировать.</span><span class="sxs-lookup"><span data-stu-id="fe027-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="fe027-105">Если на таблицу ссылаются существующие запросы, представления, определяемые пользователем функции, хранимые процедуры или программы, то удаление сделает эти объекты недействительными.</span><span class="sxs-lookup"><span data-stu-id="fe027-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="fe027-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="fe027-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fe027-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="fe027-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fe027-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fe027-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fe027-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="fe027-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fe027-110">**Удаление таблицы с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="fe027-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="fe027-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe027-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fe027-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe027-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe027-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="fe027-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fe027-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fe027-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fe027-115">Инструкцию DROP TABLE нельзя использовать для удаления таблицы, на которую ссылается ограничение FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="fe027-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="fe027-116">Сначала следует удалить ссылающееся ограничение FOREIGN KEY или ссылающуюся таблицу.</span><span class="sxs-lookup"><span data-stu-id="fe027-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="fe027-117">Если и ссылающаяся таблица, и таблица, содержащая первичный ключ, удаляются с помощью одной инструкции DROP TABLE, ссылающаяся таблица должна быть первой в списке.</span><span class="sxs-lookup"><span data-stu-id="fe027-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="fe027-118">При удалении таблицы относящиеся к ней правила и значения по умолчанию теряют привязку, а любые связанные с таблицей ограничения или триггеры автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="fe027-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="fe027-119">Если таблица будет создана заново, нужно будет заново привязать все правила и значения по умолчанию, заново создать триггеры и добавить необходимые ограничения.</span><span class="sxs-lookup"><span data-stu-id="fe027-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="fe027-120">При удалении таблицы, которая содержит столбец `varbinary (max)` с атрибутом FILESTREAM, не будут удалены какие-либо сохраненные в файловой системе данные.</span><span class="sxs-lookup"><span data-stu-id="fe027-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="fe027-121">Инструкции DROP TABLE и CREATE TABLE нельзя выполнять для одной таблицы в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="fe027-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="fe027-122">В противном случае может произойти непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fe027-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="fe027-123">Любые представления или хранимые процедуры, которые ссылаются на удаляемую таблицу, необходимо явно удалить или изменить, чтобы убрать ссылку на таблицу.</span><span class="sxs-lookup"><span data-stu-id="fe027-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe027-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="fe027-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe027-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="fe027-125">Permissions</span></span>  
 <span data-ttu-id="fe027-126">Необходимо разрешение ALTER на схему, к которой принадлежит эта таблица, разрешение CONTROL для этой таблицы или членство в предопределенной роли базы данных **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="fe027-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fe027-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe027-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="fe027-128">Удаление таблицы из базы данных</span><span class="sxs-lookup"><span data-stu-id="fe027-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="fe027-129">В обозревателе объектов выберите таблицу, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="fe027-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="fe027-130">Щелкните таблицу правой кнопкой мыши и в контекстном меню выберите **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="fe027-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="fe027-131">Появится окно подтверждения удаления.</span><span class="sxs-lookup"><span data-stu-id="fe027-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="fe027-132">Щелкните **Да**.</span><span class="sxs-lookup"><span data-stu-id="fe027-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe027-133">При удалении таблицы автоматически удаляются все связи с ней.</span><span class="sxs-lookup"><span data-stu-id="fe027-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fe027-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe027-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="fe027-135">Удаление таблицы в редакторе запросов</span><span class="sxs-lookup"><span data-stu-id="fe027-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="fe027-136">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe027-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe027-137">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="fe027-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fe027-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fe027-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="fe027-139">Дополнительные сведения см. в статье [DROP TABLE (Transact-SQL)](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fe027-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
