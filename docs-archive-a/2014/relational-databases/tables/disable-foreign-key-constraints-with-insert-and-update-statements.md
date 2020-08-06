---
title: Отключение ограничений внешнего ключа для инструкций INSERT и UPDATE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658675"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="94b25-102">Отключение ограничений внешнего ключа для инструкций INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="94b25-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="94b25-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ограничение внешнего ключа можно отключить в транзакциях INSERT и UPDATE с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b25-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="94b25-104">Используйте эту возможность, если новые данные будут нарушать существующее ограничение или если ограничение относится только к данным, уже помещенным в базу данных.</span><span class="sxs-lookup"><span data-stu-id="94b25-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="94b25-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="94b25-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="94b25-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="94b25-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="94b25-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="94b25-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="94b25-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="94b25-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="94b25-109">**Отключение ограничений внешнего ключа для инструкций INSERT и UPDATE с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="94b25-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="94b25-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94b25-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="94b25-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94b25-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94b25-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="94b25-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="94b25-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="94b25-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="94b25-114">После отключения этих ограничений будущие вставки и обновления столбца не проверяются по проверочным ограничениям.</span><span class="sxs-lookup"><span data-stu-id="94b25-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="94b25-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="94b25-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="94b25-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="94b25-116">Permissions</span></span>  
 <span data-ttu-id="94b25-117">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="94b25-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="94b25-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94b25-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="94b25-119">Отключение ограничений внешнего ключа для инструкций INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="94b25-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="94b25-120">Разверните в **обозревателе объектов**таблицу с ограничением, затем разверните папку **Ключи** .</span><span class="sxs-lookup"><span data-stu-id="94b25-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="94b25-121">Щелкните правой кнопкой мыши ограничение и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="94b25-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="94b25-122">В сетке под **конструктором таблиц**щелкните пункт **Принудительное использование ограничения внешнего ключа** и выберите значение **Нет** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="94b25-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="94b25-123">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="94b25-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="94b25-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94b25-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="94b25-125">Отключение ограничений внешнего ключа для инструкций INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="94b25-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="94b25-126">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b25-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="94b25-127">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="94b25-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="94b25-128">Скопируйте следующие примеры в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="94b25-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="94b25-129">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94b25-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
