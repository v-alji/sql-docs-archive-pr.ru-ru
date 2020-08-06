---
title: Удаление проверочного ограничения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664095"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="ab579-102">Удаление проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="ab579-102">Delete Check Constraints</span></span>
  <span data-ttu-id="ab579-103">Удалить проверочное ограничение в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab579-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ab579-104">Удаление проверочного ограничения снимает ограничения на значения данных, допустимые для столбца или столбцов, включенных в выражение ограничения.</span><span class="sxs-lookup"><span data-stu-id="ab579-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="ab579-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ab579-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab579-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ab579-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab579-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ab579-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab579-108">**Удаление проверочного ограничения с использованием:**</span><span class="sxs-lookup"><span data-stu-id="ab579-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="ab579-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab579-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ab579-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab579-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab579-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ab579-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab579-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="ab579-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab579-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="ab579-113">Permissions</span></span>  
 <span data-ttu-id="ab579-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="ab579-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab579-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab579-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="ab579-116">Удаление проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="ab579-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="ab579-117">В **Обозревателе объектов**разверните таблицу с проверочным ограничением.</span><span class="sxs-lookup"><span data-stu-id="ab579-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="ab579-118">Разверните  **Ограничения**.</span><span class="sxs-lookup"><span data-stu-id="ab579-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="ab579-119">Щелкните ограничение правой кнопкой мыши и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ab579-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="ab579-120">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ab579-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ab579-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab579-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="ab579-122">Удаление проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="ab579-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="ab579-123">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab579-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab579-124">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ab579-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ab579-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ab579-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="ab579-126">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab579-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
