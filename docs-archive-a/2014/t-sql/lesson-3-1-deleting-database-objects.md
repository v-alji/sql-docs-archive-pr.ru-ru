---
title: Удаление объектов базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655511"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="f03e7-102">Удаление объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="f03e7-102">Deleting Database Objects</span></span>
  <span data-ttu-id="f03e7-103">Чтобы удалить все записи, созданные при использовании учебника, достаточно удалить базу данных.</span><span class="sxs-lookup"><span data-stu-id="f03e7-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="f03e7-104">Тем не менее, в данном разделе будет показано, как аннулировать любое действие, совершенное при выполнении заданий из этого учебника.</span><span class="sxs-lookup"><span data-stu-id="f03e7-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="f03e7-105">Удаление разрешений и объектов</span><span class="sxs-lookup"><span data-stu-id="f03e7-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="f03e7-106">Перед удалением объектов необходимо убедиться, что используется нужная база данных:</span><span class="sxs-lookup"><span data-stu-id="f03e7-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="f03e7-107">С помощью инструкции `REVOKE` удаляется разрешение на выполнение, предоставленное `Mary` на хранимую процедуру:</span><span class="sxs-lookup"><span data-stu-id="f03e7-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="f03e7-108">С помощью инструкции `DROP` удаляется разрешение, предоставленное `Mary` для доступа к базе данных `TestData` :</span><span class="sxs-lookup"><span data-stu-id="f03e7-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="f03e7-109">С помощью инструкции `DROP` удаляется разрешение, предоставленное `Mary` для доступа к экземпляру [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f03e7-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="f03e7-110">С помощью инструкции `DROP` удаляется хранимая процедура `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="f03e7-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="f03e7-111">С помощью инструкции `DROP` удаляется представление `vw_Names`:</span><span class="sxs-lookup"><span data-stu-id="f03e7-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="f03e7-112">С помощью инструкции `DELETE` удаляются все строки таблицы `Products` :</span><span class="sxs-lookup"><span data-stu-id="f03e7-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="f03e7-113">С помощью инструкции `DROP` удаляется таблица `Products` :</span><span class="sxs-lookup"><span data-stu-id="f03e7-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="f03e7-114">Базу данных `TestData` невозможно удалить во время нахождения в ней; поэтому сначала требуется переключить контекст на другую базу данных и только после этого с помощью инструкции `DROP` удалить базу данных `TestData` :</span><span class="sxs-lookup"><span data-stu-id="f03e7-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="f03e7-115">Это заключительный шаг учебника «Составление инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="f03e7-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="f03e7-116">Помните, что этот учебник содержит только краткий обзор и не включает описания всех параметров используемых инструкций.</span><span class="sxs-lookup"><span data-stu-id="f03e7-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="f03e7-117">Для проектирования и создания эффективной структуры базы данных и настройки безопасного доступа к данным требуется более сложная база данных, чем показанная в примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="f03e7-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="f03e7-118">Возвращение к порталу средств SQL Server</span><span class="sxs-lookup"><span data-stu-id="f03e7-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="f03e7-119">Руководство. Составление инструкций Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f03e7-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="f03e7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="f03e7-120">See Also</span></span>  
 <span data-ttu-id="f03e7-121">[REVOKE (Transact-SQL)](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-122">[DROP USER (Transact-SQL)](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-123">[DROP LOGIN &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-124">[УДАЛИТЬ процедуру &#40;языке Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-125">[DROP VIEW (Transact-SQL)](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-126">[DELETE (Transact-SQL)](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="f03e7-127">[DROP TABLE (Transact-SQL)](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f03e7-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="f03e7-128">DROP DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f03e7-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
