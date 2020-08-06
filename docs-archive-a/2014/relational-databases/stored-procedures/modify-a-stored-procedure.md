---
title: Изменение хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728126"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="31d4a-102">Изменение хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="31d4a-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="31d4a-103">В этом разделе описывается, как изменить хранимую процедуру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31d4a-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="31d4a-104">**Перед началом работы**  [Ограничения](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="31d4a-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="31d4a-105">**Изменение хранимой процедуры с использованием:**  [среды SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="31d4a-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="31d4a-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="31d4a-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="31d4a-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="31d4a-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="31d4a-108">Хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] нельзя преобразовать в хранимые процедуры CLR, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="31d4a-108">[!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="31d4a-109">Если предыдущее определение процедуры было создано с параметрами WITH ENCRYPTION или WITH RECOMPILE, эти параметры будут включены только в случае, если они указаны в инструкции ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="31d4a-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="31d4a-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="31d4a-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="31d4a-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="31d4a-111">Permissions</span></span>  
 <span data-ttu-id="31d4a-112">Необходимо разрешение ALTER PROCEDURE на процедуру.</span><span class="sxs-lookup"><span data-stu-id="31d4a-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="31d4a-113">Изменение хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="31d4a-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="31d4a-114">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="31d4a-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="31d4a-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31d4a-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="31d4a-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31d4a-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="31d4a-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31d4a-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="31d4a-118">**Изменение процедуры в среде Management Studio**</span><span class="sxs-lookup"><span data-stu-id="31d4a-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="31d4a-119">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="31d4a-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="31d4a-120">Последовательно разверните узел **Базы данных**, базу данных, которой принадлежит процедура, и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="31d4a-121">Разверните **Хранимые процедуры**, щелкните правой кнопкой мыши изменяемую процедуру, затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="31d4a-122">Изменение текста хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="31d4a-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="31d4a-123">Для проверки синтаксиса выберите пункт **Выполнить анализ** в меню **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="31d4a-124">Чтобы сохранить изменения определения процедуры, в меню **Запрос** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="31d4a-125">Чтобы сохранить обновленное определение процедуры в качестве скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] , в меню **Файл** выберите команду **Сохранить как...**</span><span class="sxs-lookup"><span data-stu-id="31d4a-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="31d4a-126">Можно принять предложенное имя файла или заменить его новым, после чего следует нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="31d4a-127">Проверяйте все данные, вводимые пользователем.</span><span class="sxs-lookup"><span data-stu-id="31d4a-127">Validate all user input.</span></span> <span data-ttu-id="31d4a-128">Не включайте их в сценарий, не выполнив проверку.</span><span class="sxs-lookup"><span data-stu-id="31d4a-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="31d4a-129">Никогда не выполняйте команду, построенную на основании непроверенных пользовательских входных данных.</span><span class="sxs-lookup"><span data-stu-id="31d4a-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="31d4a-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31d4a-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="31d4a-131">**Изменение процедуры в редакторе запросов**</span><span class="sxs-lookup"><span data-stu-id="31d4a-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="31d4a-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="31d4a-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="31d4a-133">Разверните узел **Базы данных**, разверните базу данных, в которой находится процедура.</span><span class="sxs-lookup"><span data-stu-id="31d4a-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="31d4a-134">Также можно выбрать необходимую базу данных из списка доступных баз данных на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="31d4a-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="31d4a-135">В данном примере выберите базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31d4a-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="31d4a-136">В меню **Файл** выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="31d4a-137">Скопируйте и вставьте следующий пример в редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="31d4a-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="31d4a-138">В этом примере будет создана процедура `uspVendorAllInfo` , которая возвращает для всех поставщиков в базе данных [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] их имена, поставляемую продукцию, кредитные рейтинги и доступность.</span><span class="sxs-lookup"><span data-stu-id="31d4a-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="31d4a-139">В меню **Файл** выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="31d4a-140">Скопируйте и вставьте следующий пример в редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="31d4a-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="31d4a-141">В следующем примере изменяется процедура `uspVendorAllInfo` .</span><span class="sxs-lookup"><span data-stu-id="31d4a-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="31d4a-142">Предложение EXECUTE AS CALLER удаляется, и изменяется текст процедуры, чтобы возвращать только поставщиков, предлагающих конкретный товар.</span><span class="sxs-lookup"><span data-stu-id="31d4a-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="31d4a-143">Содержимое результирующего набора определяется при помощи функций `LEFT` и `CASE`.</span><span class="sxs-lookup"><span data-stu-id="31d4a-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="31d4a-144">Чтобы сохранить изменения определения процедуры, в меню **Запрос** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="31d4a-145">Чтобы сохранить обновленное определение процедуры в качестве скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] , в меню **Файл** выберите команду **Сохранить как...**</span><span class="sxs-lookup"><span data-stu-id="31d4a-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="31d4a-146">Можно принять предложенное имя файла или заменить его новым, после чего следует нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="31d4a-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="31d4a-147">Чтобы выполнить измененную хранимую процедуру, выполните следующий пример.</span><span class="sxs-lookup"><span data-stu-id="31d4a-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31d4a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="31d4a-148">See Also</span></span>  
 [<span data-ttu-id="31d4a-149">ALTER PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="31d4a-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
