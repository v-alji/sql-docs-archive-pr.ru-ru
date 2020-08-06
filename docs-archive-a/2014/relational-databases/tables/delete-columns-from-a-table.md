---
title: Удаление столбцов из таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665251"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="822a6-102">Удаление столбцов из таблицы</span><span class="sxs-lookup"><span data-stu-id="822a6-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="822a6-103">В этом разделе приведены инструкции по удалению столбцов таблиц в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822a6-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="822a6-104">При удалении столбца из таблицы этот столбец и все содержащиеся в нем данные удаляются из базы данных.</span><span class="sxs-lookup"><span data-stu-id="822a6-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="822a6-105">Это действие невозможно отменить.</span><span class="sxs-lookup"><span data-stu-id="822a6-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="822a6-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="822a6-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="822a6-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="822a6-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="822a6-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="822a6-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="822a6-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="822a6-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="822a6-110">**Удаление столбца из таблицы с помощью:**</span><span class="sxs-lookup"><span data-stu-id="822a6-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="822a6-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="822a6-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="822a6-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="822a6-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="822a6-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="822a6-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="822a6-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="822a6-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="822a6-115">Нельзя удалить столбец, имеющий ограничение CHECK.</span><span class="sxs-lookup"><span data-stu-id="822a6-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="822a6-116">В первую очередь необходимо удалить ограничение.</span><span class="sxs-lookup"><span data-stu-id="822a6-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="822a6-117">Удалить столбец, имеющий ограничения PRIMARY KEY, FOREIGN KEY или другие зависимости можно только с использованием конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="822a6-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="822a6-118">При использовании обозревателя объектов или [!INCLUDE[tsql](../../includes/tsql-md.md)]необходимо в первую очередь удалить зависимости столбца.</span><span class="sxs-lookup"><span data-stu-id="822a6-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="822a6-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="822a6-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="822a6-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="822a6-120">Permissions</span></span>  
 <span data-ttu-id="822a6-121">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="822a6-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="822a6-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="822a6-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="822a6-123">Удаление столбцов с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="822a6-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="822a6-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822a6-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="822a6-125">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, из которой необходимо удалить столбцы, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="822a6-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="822a6-126">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="822a6-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="822a6-127">Если столбец содержит ограничения или другие зависимости, то в диалоговом окне **Удаление объекта** будет отображено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="822a6-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="822a6-128">Чтобы устранить проблему, удалите упомянутые ограничения.</span><span class="sxs-lookup"><span data-stu-id="822a6-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="822a6-129">Удаление столбцов с использованием конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="822a6-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="822a6-130">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, из которой необходимо удалить столбцы, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="822a6-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="822a6-131">Щелкните правой кнопкой мыши столбец, который надо удалить, и выберите из контекстного меню пункт **Удалить столбец** .</span><span class="sxs-lookup"><span data-stu-id="822a6-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="822a6-132">Если столбец участвует в связи (FOREIGN KEY или PRIMARY KEY), то будет выдано сообщение с запросом на подтверждение удаления выбранных столбцов и их связей.</span><span class="sxs-lookup"><span data-stu-id="822a6-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="822a6-133">выберите **Yes** (Да).</span><span class="sxs-lookup"><span data-stu-id="822a6-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="822a6-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="822a6-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="822a6-135">Удаление столбцов</span><span class="sxs-lookup"><span data-stu-id="822a6-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="822a6-136">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822a6-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="822a6-137">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="822a6-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="822a6-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="822a6-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="822a6-139">Если столбец содержит ограничения или другие зависимости, то будет возвращено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="822a6-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="822a6-140">Чтобы устранить проблему, удалите упомянутые ограничения.</span><span class="sxs-lookup"><span data-stu-id="822a6-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="822a6-141">Дополнительные примеры см. в статье [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="822a6-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
