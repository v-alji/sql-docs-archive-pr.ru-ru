---
title: Отключение проверочных ограничений в инструкциях INSERT и UPDATE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664086"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="452a7-102">Отключение проверочных ограничений в инструкциях INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="452a7-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="452a7-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] проверочное ограничение можно отключить в транзакциях INSERT и UPDATE с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="452a7-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="452a7-104">После отключения проверочных ограничений будущие вставки и обновления столбца не проверяются по проверочным ограничениям.</span><span class="sxs-lookup"><span data-stu-id="452a7-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="452a7-105">Используйте эту возможность, если новые данные будут нарушать существующее ограничение или если ограничение относится только к данным, уже помещенным в базу данных.</span><span class="sxs-lookup"><span data-stu-id="452a7-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="452a7-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="452a7-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="452a7-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="452a7-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="452a7-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="452a7-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="452a7-109">**Отключение проверочного ограничения в инструкциях INSERT и UPDATE с помощью:**</span><span class="sxs-lookup"><span data-stu-id="452a7-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="452a7-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="452a7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="452a7-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="452a7-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="452a7-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="452a7-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="452a7-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="452a7-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="452a7-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="452a7-114">Permissions</span></span>  
 <span data-ttu-id="452a7-115">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="452a7-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="452a7-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="452a7-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="452a7-117">Отключение проверочного ограничения при выполнении инструкций INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="452a7-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="452a7-118">Разверните в **Обозревателе объектов**таблицу с ограничением, затем раскройте папку **Ограничения** .</span><span class="sxs-lookup"><span data-stu-id="452a7-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="452a7-119">Щелкните правой кнопкой мыши ограничение и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="452a7-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="452a7-120">В сетке под **конструктором таблиц**щелкните пункт **Применять при операциях INSERT и UPDATE** и выберите значение **Нет** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="452a7-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="452a7-121">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="452a7-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="452a7-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="452a7-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="452a7-123">Отключение проверочного ограничения при выполнении инструкций INSERT и UPDATE</span><span class="sxs-lookup"><span data-stu-id="452a7-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="452a7-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="452a7-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="452a7-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="452a7-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="452a7-126">Скопируйте следующие примеры в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="452a7-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="452a7-127">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="452a7-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
