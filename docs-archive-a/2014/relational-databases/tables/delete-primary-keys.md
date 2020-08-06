---
title: Удаление первичных ключей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669348"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="a1636-102">Удаление первичных ключей</span><span class="sxs-lookup"><span data-stu-id="a1636-102">Delete Primary Keys</span></span>
  <span data-ttu-id="a1636-103">Удалить первичный ключ в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1636-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a1636-104">При удалении первичного ключа удаляется и соответствующий индекс.</span><span class="sxs-lookup"><span data-stu-id="a1636-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="a1636-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a1636-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a1636-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a1636-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a1636-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a1636-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a1636-108">**Удаление первичного ключа с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="a1636-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="a1636-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1636-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a1636-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a1636-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a1636-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a1636-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a1636-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="a1636-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a1636-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="a1636-113">Permissions</span></span>  
 <span data-ttu-id="a1636-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="a1636-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a1636-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1636-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="a1636-116">Удаление ограничения первичного ключа с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="a1636-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="a1636-117">В Обозревателе объектов разверните таблицу, которая содержит первичный ключ, и разверните узел **Ключи**.</span><span class="sxs-lookup"><span data-stu-id="a1636-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="a1636-118">Щелкните ключ правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a1636-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="a1636-119">В диалоговом окне **Удаление объекта** убедитесь в том, что выбран правильный ключ, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a1636-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="a1636-120">Удаление ограничения первичного ключа с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="a1636-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="a1636-121">В обозревателе объектов щелкните таблицу с первичным ключом правой кнопкой мыши и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="a1636-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="a1636-122">В сетке таблицы щелкните правой кнопкой строку с первичным ключом и выберите пункт **Удалить первичный ключ** , чтобы переключить параметр.</span><span class="sxs-lookup"><span data-stu-id="a1636-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1636-123">Чтобы отменить это действие, закройте таблицу, не сохраняя изменений.</span><span class="sxs-lookup"><span data-stu-id="a1636-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="a1636-124">Удаление первичного ключа не может быть отменено без потери всех других изменений, сделанных в таблице.</span><span class="sxs-lookup"><span data-stu-id="a1636-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="a1636-125">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="a1636-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a1636-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a1636-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="a1636-127">Удаление ограничения первичного ключа</span><span class="sxs-lookup"><span data-stu-id="a1636-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="a1636-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1636-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a1636-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a1636-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a1636-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a1636-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a1636-131">В этом примере сначала определяется имя ограничения первичного ключа, а затем удаляется ограничение.</span><span class="sxs-lookup"><span data-stu-id="a1636-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="a1636-132">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) и [sys.key_constraints (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="a1636-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
