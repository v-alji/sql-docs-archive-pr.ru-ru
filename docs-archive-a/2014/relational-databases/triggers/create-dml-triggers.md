---
title: Создание триггеров DML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668155"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="58eeb-102">Создание триггеров DML</span><span class="sxs-lookup"><span data-stu-id="58eeb-102">Create DML Triggers</span></span>
  <span data-ttu-id="58eeb-103">В этом разделе описано, как создать триггер DML [!INCLUDE[tsql](../../includes/tsql-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER.</span><span class="sxs-lookup"><span data-stu-id="58eeb-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="58eeb-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="58eeb-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="58eeb-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="58eeb-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="58eeb-106">Список ограничений, связанных с созданием триггеров DML, см. в разделе [CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58eeb-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="58eeb-107">Permissions</span><span class="sxs-lookup"><span data-stu-id="58eeb-107">Permissions</span></span>  
 <span data-ttu-id="58eeb-108">Требует разрешения ALTER на таблицу или представление, на которых создается триггер.</span><span class="sxs-lookup"><span data-stu-id="58eeb-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="58eeb-109">Как создать триггер DML</span><span class="sxs-lookup"><span data-stu-id="58eeb-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="58eeb-110">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="58eeb-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="58eeb-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="58eeb-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="58eeb-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58eeb-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="58eeb-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="58eeb-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="58eeb-114">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="58eeb-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="58eeb-115">Разверните узел **Базы данных**, разверните базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , разверните узел **Таблицы** , а затем таблицу **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="58eeb-116">Правой кнопкой мыши щелкните элемент **Триггеры**, а затем выберите пункт **Создать триггер**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="58eeb-117">В меню **Запрос** выберите пункт **Указать значения для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="58eeb-118">Можно также нажать клавиши CTRL-SHIFT-M, чтобы открыть диалоговое окно **Задание значений для параметров шаблона** .</span><span class="sxs-lookup"><span data-stu-id="58eeb-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="58eeb-119">В диалоговом окне **Задание значений для параметров шаблона** введите для показанных параметров следующие значения.</span><span class="sxs-lookup"><span data-stu-id="58eeb-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="58eeb-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="58eeb-120">Parameter</span></span>|<span data-ttu-id="58eeb-121">Значение</span><span class="sxs-lookup"><span data-stu-id="58eeb-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="58eeb-122">Автор</span><span class="sxs-lookup"><span data-stu-id="58eeb-122">Author</span></span>|<span data-ttu-id="58eeb-123">*Ваше имя*</span><span class="sxs-lookup"><span data-stu-id="58eeb-123">*Your name*</span></span>|  
    |<span data-ttu-id="58eeb-124">Дата создания</span><span class="sxs-lookup"><span data-stu-id="58eeb-124">Create Date</span></span>|<span data-ttu-id="58eeb-125">*Сегодняшняя дата*</span><span class="sxs-lookup"><span data-stu-id="58eeb-125">*Today's date*</span></span>|  
    |<span data-ttu-id="58eeb-126">Description</span><span class="sxs-lookup"><span data-stu-id="58eeb-126">Description</span></span>|<span data-ttu-id="58eeb-127">Проверяет кредитоспособность поставщика, прежде чем позволить вставить новый заказ на покупку от этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="58eeb-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="58eeb-128">Имя_схемы</span><span class="sxs-lookup"><span data-stu-id="58eeb-128">Schema_Name</span></span>|<span data-ttu-id="58eeb-129">Приобретение</span><span class="sxs-lookup"><span data-stu-id="58eeb-129">Purchasing</span></span>|  
    |<span data-ttu-id="58eeb-130">Имя_триггера</span><span class="sxs-lookup"><span data-stu-id="58eeb-130">Trigger_Name</span></span>|<span data-ttu-id="58eeb-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="58eeb-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="58eeb-132">Имя_таблицы</span><span class="sxs-lookup"><span data-stu-id="58eeb-132">Table_Name</span></span>|<span data-ttu-id="58eeb-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="58eeb-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="58eeb-134">Команда_изменения_данных</span><span class="sxs-lookup"><span data-stu-id="58eeb-134">Data_Modification_Statement</span></span>|<span data-ttu-id="58eeb-135">Удаление инструкций UPDATE и DELETE из списка.</span><span class="sxs-lookup"><span data-stu-id="58eeb-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="58eeb-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="58eeb-137">В **редакторе запросов**замените комментарий `-- Insert statements for trigger here` следующей инструкцией:</span><span class="sxs-lookup"><span data-stu-id="58eeb-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
  
8.  <span data-ttu-id="58eeb-138">Чтобы проверить синтаксис, в меню **Запрос** выберите пункт **Синтаксический анализ**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="58eeb-139">Если появится сообщение об ошибке, сравните эту инструкцию с вышеуказанной информацией, внесите исправления и повторите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="58eeb-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="58eeb-140">Чтобы создать триггер DML, в меню **Запрос** нажмите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="58eeb-141">Триггер DML создается как объект в базе данных.</span><span class="sxs-lookup"><span data-stu-id="58eeb-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="58eeb-142">Чтобы увидеть этот триггер DML в обозревателе объектов, щелкните правой кнопкой мыши элемент **Триггеры** и выберите пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="58eeb-143">Перед началом</span><span class="sxs-lookup"><span data-stu-id="58eeb-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="58eeb-144">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58eeb-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="58eeb-145">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="58eeb-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="58eeb-146">В меню **Файл** выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="58eeb-147">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="58eeb-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="58eeb-148">В этом примере создается такой же хранимый триггер DML, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="58eeb-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
    -- Trigger valid for multirow and single row inserts  
    -- and optimal for single row inserts.  
    USE AdventureWorks2012;  
    GO  
    CREATE TRIGGER NewPODetail3  
    ON Purchasing.PurchaseOrderDetail  
    FOR INSERT AS  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
