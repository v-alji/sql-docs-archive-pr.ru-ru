---
title: Выполнение определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669340"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="351dc-102">Выполнение определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="351dc-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="351dc-103">Определяемую пользователем функцию можно выполнить в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="351dc-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="351dc-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="351dc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="351dc-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="351dc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="351dc-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="351dc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="351dc-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="351dc-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="351dc-108">**Для выполнения определяемой пользователем функции используется:**</span><span class="sxs-lookup"><span data-stu-id="351dc-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="351dc-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="351dc-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="351dc-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="351dc-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="351dc-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="351dc-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="351dc-112">В Transact-SQL параметры могут передаваться через *value* или с помощью @*parameter_name*=*value.*</span><span class="sxs-lookup"><span data-stu-id="351dc-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="351dc-113">. Параметр не является частью транзакции, поэтому если он изменился в транзакции, которая впоследствии подверглась откату, то прежнее значение параметра не восстанавливается.</span><span class="sxs-lookup"><span data-stu-id="351dc-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="351dc-114">Возвращаемым вызывающему значением всегда является то значение, которое существует на момент выхода из модуля.</span><span class="sxs-lookup"><span data-stu-id="351dc-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="351dc-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="351dc-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="351dc-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="351dc-116">Permissions</span></span>  
 <span data-ttu-id="351dc-117">На выполнение инструкции EXECUTE разрешения не требуются.</span><span class="sxs-lookup"><span data-stu-id="351dc-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="351dc-118">Однако необходимы разрешения на защищаемые объекты, на которые ссылается командная строка в инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="351dc-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="351dc-119">Например, если строка содержит инструкцию INSERT, вызывающий инструкцию EXECUTE пользователь должен иметь разрешение INSERT на целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="351dc-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="351dc-120">Разрешения проверяются в месте нахождения инструкции EXECUTE, даже если она содержится внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="351dc-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="351dc-121">Дополнительные сведения см. в разделе [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="351dc-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="351dc-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="351dc-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="351dc-123">Выполнение определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="351dc-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="351dc-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="351dc-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="351dc-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="351dc-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="351dc-126">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="351dc-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="351dc-127">Дополнительные сведения см. в разделе [EXECUTE (Transact-SQL)](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="351dc-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
