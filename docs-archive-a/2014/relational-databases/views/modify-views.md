---
title: Изменение представлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- views [SQL Server], modifying
- modifying views
- renaming views
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10cf9ecc860d8f9b46a06ac679b0f1a8241000bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664077"
---
# <a name="modify-views"></a><span data-ttu-id="f3434-102">Изменение представлений</span><span class="sxs-lookup"><span data-stu-id="f3434-102">Modify Views</span></span>
  <span data-ttu-id="f3434-103">После определения представления это определение можно изменить в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] без удаления и повторного создания представления с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3434-103">After you define a view, you can modify its definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] without dropping and re-creating the view by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f3434-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f3434-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3434-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f3434-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3434-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3434-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f3434-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f3434-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3434-108">**Изменение представления с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="f3434-108">**To modify a view, using:**</span></span>  
  
     [<span data-ttu-id="f3434-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3434-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3434-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3434-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3434-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f3434-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f3434-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3434-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f3434-113">Изменение представлений не влияет ни на какие зависимые объекты, например хранимые процедуры или триггеры, до тех пор пока определение представления не будет изменено таким образом, что зависимый объект станет недопустимым.</span><span class="sxs-lookup"><span data-stu-id="f3434-113">Modifying a view does not affect any dependent objects, such as stored procedures or triggers, unless the definition of the view changes in such a way that the dependent object is no longer valid.</span></span>  
  
-   <span data-ttu-id="f3434-114">При изменении текущего представления с помощью инструкции ALTER VIEW компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] осуществляет монопольную блокировку схемы представления.</span><span class="sxs-lookup"><span data-stu-id="f3434-114">If a view currently used is modified by using ALTER VIEW, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes an exclusive schema lock on the view.</span></span> <span data-ttu-id="f3434-115">Если блокировка предоставлена, и с представлением в настоящий момент не работает ни один пользователь, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] удаляет все копии представления из кэша процедур.</span><span class="sxs-lookup"><span data-stu-id="f3434-115">When the lock is granted, and there are no active users of the view, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] deletes all copies of the view from the procedure cache.</span></span> <span data-ttu-id="f3434-116">Существующие планы, ссылающиеся на представление, остаются в кэше, но при обращении к ним выполняется повторная компиляция.</span><span class="sxs-lookup"><span data-stu-id="f3434-116">Existing plans referencing the view remain in the cache but are recompiled when invoked.</span></span>  
  
-   <span data-ttu-id="f3434-117">Инструкцию ALTER VIEW можно выполнять для индексированных представлений, однако она удаляет все индексы представления.</span><span class="sxs-lookup"><span data-stu-id="f3434-117">ALTER VIEW can be applied to indexed views; however, ALTER VIEW unconditionally drops all indexes on the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3434-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="f3434-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3434-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="f3434-119">Permissions</span></span>  
 <span data-ttu-id="f3434-120">Для выполнения инструкции ALTER VIEW необходимо как минимум разрешение ALTER на объект.</span><span class="sxs-lookup"><span data-stu-id="f3434-120">To execute ALTER VIEW, at a minimum, ALTER permission on OBJECT is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3434-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3434-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="f3434-122">Изменение представления</span><span class="sxs-lookup"><span data-stu-id="f3434-122">To modify a view</span></span>  
  
1.  <span data-ttu-id="f3434-123">В **обозревателе объектов**щелкните знак «плюс» рядом с базой данных, в которой содержится представление, а затем щелкните знак «плюс» рядом с папкой **Представления** .</span><span class="sxs-lookup"><span data-stu-id="f3434-123">In **Object Explorer**, click the plus sign next to the database where your view is located and then click the plus sign next to the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="f3434-124">Щелкните правой кнопкой мыши представление, которое нужно изменить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="f3434-124">Right-click on the view you wish to modify and select **Design**.</span></span>  
  
3.  <span data-ttu-id="f3434-125">На панели диаграмм конструктора запросов внесите изменения в представление одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f3434-125">In the diagram pane of the query designer, make changes to the view in one or more of the following ways:</span></span>  
  
    1.  <span data-ttu-id="f3434-126">Установите или снимите флажки элементов, которые необходимо добавить или удалить.</span><span class="sxs-lookup"><span data-stu-id="f3434-126">Select or clear the check boxes of any elements you wish to add or remove.</span></span>  
  
    2.  <span data-ttu-id="f3434-127">Щелкните правой кнопкой мыши на панели диаграмм, выберите **Добавить таблицу…** , а затем выберите дополнительные столбцы, которые необходимо добавить к представлению, в диалоговом окне **Добавить таблицу**.</span><span class="sxs-lookup"><span data-stu-id="f3434-127">Right-click within the diagram pane, select **Add Table...**, and then select the additional columns you want to add to the view from the **Add Table** dialog box.</span></span>  
  
    3.  <span data-ttu-id="f3434-128">Щелкните правой кнопкой мыши строку заголовка таблицы, которую необходимо удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3434-128">Right-click the title bar of the table you wish to remove and select **Remove**.</span></span>  
  
4.  <span data-ttu-id="f3434-129">В меню **Файл** выберите пункт **Сохранить**_view name_.</span><span class="sxs-lookup"><span data-stu-id="f3434-129">On the **File** menu, click **Save**_view name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3434-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3434-130">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-view"></a><span data-ttu-id="f3434-131">Изменение представления</span><span class="sxs-lookup"><span data-stu-id="f3434-131">To modify a view</span></span>  
  
1.  <span data-ttu-id="f3434-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3434-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3434-133">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f3434-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3434-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3434-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f3434-135">В этом примере сначала создается представление, а затем оно изменяется с помощью инструкции ALTER VIEW.</span><span class="sxs-lookup"><span data-stu-id="f3434-135">The example first creates a view and then modifies the view by using ALTER VIEW.</span></span> <span data-ttu-id="f3434-136">Предложение WHERE добавляется к определению представления.</span><span class="sxs-lookup"><span data-stu-id="f3434-136">A WHERE clause is added to the view definition.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 <span data-ttu-id="f3434-137">Дополнительные сведения см. в разделе [ALTER VIEW (Transact-SQL)](/sql/t-sql/statements/alter-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3434-137">For more information, see [ALTER VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-view-transact-sql).</span></span>  
  
  
