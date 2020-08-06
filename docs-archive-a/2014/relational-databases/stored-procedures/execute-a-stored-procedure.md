---
title: Выполнение хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667619"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="5fac2-102">Выполнение хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="5fac2-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="5fac2-103">В этом разделе описывается, как выполнить хранимую процедуру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fac2-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5fac2-104">Существует два способа выполнения хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="5fac2-105">Первым и наиболее распространенным подходом является вызов процедуры приложением или пользователем.</span><span class="sxs-lookup"><span data-stu-id="5fac2-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="5fac2-106">Второй подход — настройка автоматического выполнения процедуры при запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fac2-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="5fac2-107">Если процедура вызывается приложением или пользователем, то в вызове явно указывается ключевое слово [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE или EXEC.</span><span class="sxs-lookup"><span data-stu-id="5fac2-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="5fac2-108">Процедуру также можно вызывать и выполнять без ключевого слова, если она является первой инструкцией в пакете [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fac2-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="5fac2-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5fac2-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5fac2-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5fac2-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5fac2-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5fac2-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5fac2-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5fac2-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5fac2-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5fac2-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5fac2-114">**Для выполнения хранимой процедуры используется:**</span><span class="sxs-lookup"><span data-stu-id="5fac2-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="5fac2-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fac2-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5fac2-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5fac2-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5fac2-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5fac2-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5fac2-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5fac2-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5fac2-119">При сопоставлении имен системных процедур используются параметры сортировки вызывающей базы данных.</span><span class="sxs-lookup"><span data-stu-id="5fac2-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="5fac2-120">Таким образом, в вызове процедур следует всегда использовать точный регистр имен системных процедур.</span><span class="sxs-lookup"><span data-stu-id="5fac2-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="5fac2-121">Например, этот код завершится с ошибкой при выполнении в контексте базы данных, в параметрах сортировки которой учитывается регистр:</span><span class="sxs-lookup"><span data-stu-id="5fac2-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="5fac2-122">Чтобы показать точные имена системных процедур, запросите представления каталога [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) и [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5fac2-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="5fac2-123">Если определяемая пользователем процедура имеет имя, совпадающее с системной процедурой, то такая определяемая пользователем процедура никогда не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="5fac2-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5fac2-124">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5fac2-124">Recommendations</span></span>  
  
-   <span data-ttu-id="5fac2-125">Выполнение системных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="5fac2-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="5fac2-126">Имена системных процедур начинаются с префикса **sp_** .</span><span class="sxs-lookup"><span data-stu-id="5fac2-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="5fac2-127">Поскольку они логически отображаются во всех базах данных, определяемых и пользователем и системой, то они могут выполняться из любой базы данных без полного указания имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="5fac2-128">Однако рекомендуется уточнять имена всех системных процедур указанием схемы **sys** во избежание конфликтов имен.</span><span class="sxs-lookup"><span data-stu-id="5fac2-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="5fac2-129">В следующем примере демонстрируется рекомендуемый метод вызова системной процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="5fac2-130">Выполнение пользовательских хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="5fac2-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="5fac2-131">При выполнении определяемой пользователем процедуры рекомендуется дополнительно указывать имя схемы.</span><span class="sxs-lookup"><span data-stu-id="5fac2-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="5fac2-132">Это позволяет немного увеличить производительность, поскольку компоненту [!INCLUDE[ssDE](../../../includes/ssde-md.md)] не нужно выполнять поиск в нескольких схемах.</span><span class="sxs-lookup"><span data-stu-id="5fac2-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="5fac2-133">Также исключается выполнение неправильной процедуры в случае, если в нескольких схемах базы данных имеются процедуры с одним именем.</span><span class="sxs-lookup"><span data-stu-id="5fac2-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="5fac2-134">В следующем примере демонстрируется рекомендуемый метод выполнения определяемой пользователем процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="5fac2-135">Обратите внимание, что процедура принимает один входной параметр.</span><span class="sxs-lookup"><span data-stu-id="5fac2-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="5fac2-136">Сведения об указании входных и выходных параметров см. в статье [Указание параметров](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5fac2-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="5fac2-137">-Или-</span><span class="sxs-lookup"><span data-stu-id="5fac2-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="5fac2-138">Если не указано уточненное имя определяемой пользователем процедуры, компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] производит поиск процедуры в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="5fac2-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="5fac2-139">схема **sys** текущей базы данных;</span><span class="sxs-lookup"><span data-stu-id="5fac2-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="5fac2-140">Схема по умолчанию вызывающей программы при выполнении в пакете или в динамическом коде SQL.</span><span class="sxs-lookup"><span data-stu-id="5fac2-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="5fac2-141">Если неуточненное имя процедуры присутствует в тексте определения другой процедуры, в следующую очередь выполняется поиск в схеме, содержащей другую процедуру.</span><span class="sxs-lookup"><span data-stu-id="5fac2-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="5fac2-142">Схема **dbo** в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="5fac2-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="5fac2-143">Автоматическое выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="5fac2-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="5fac2-144">Процедуры, помеченные для автоматического выполнения, выполняются каждый раз, когда запускается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и в процессе запуска восстанавливается база данных **master** .</span><span class="sxs-lookup"><span data-stu-id="5fac2-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="5fac2-145">Настройка процедур для автоматического выполнения удобна для операций обслуживания базы данных и для постоянного выполнения процедур в фоновом процессе.</span><span class="sxs-lookup"><span data-stu-id="5fac2-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="5fac2-146">Кроме того, автоматический запуск процедур может применяться для выполнения системных или служебных задач в базе данных **tempdb**, таких как создание глобальной временной таблицы.</span><span class="sxs-lookup"><span data-stu-id="5fac2-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="5fac2-147">Это обеспечивает наличие такой временной таблицы при повторном создании базы данных **tempdb** во время запуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fac2-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="5fac2-148">Автоматически выполняемая процедура работает с теми же разрешениями, что и члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5fac2-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="5fac2-149">Любое сообщение об ошибке, сформированное такой процедурой, записывается в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fac2-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="5fac2-150">Ограничений на количество автоматически запускаемых процедур не существует, однако помните, что для выполнения каждой необходим один рабочий поток.</span><span class="sxs-lookup"><span data-stu-id="5fac2-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="5fac2-151">Если необходимо выполнить несколько процедур при запуске, которые не должны выполняться параллельно, настройте одну процедуру на автоматический запуск, а вторую вызывайте в ее теле (в конце).</span><span class="sxs-lookup"><span data-stu-id="5fac2-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="5fac2-152">Таким образом будет задействован только один рабочий поток.</span><span class="sxs-lookup"><span data-stu-id="5fac2-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="5fac2-153">Не возвращайте никаких результирующих наборов из автоматически запускаемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="5fac2-154">Эта хранимая процедура выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а не приложением или пользователем, и поэтому результирующие наборы нигде не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="5fac2-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="5fac2-155">Установка, очистка и контроль автоматического выполнения</span><span class="sxs-lookup"><span data-stu-id="5fac2-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="5fac2-156">Помечать процедуру для автоматического выполнения может только системный администратор (**sa**).</span><span class="sxs-lookup"><span data-stu-id="5fac2-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="5fac2-157">Кроме того, процедура должна находиться в базе данных **master** , принадлежать пользователю **sa**и не иметь входных или выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="5fac2-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="5fac2-158">Используйте процедуру [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) чтобы:</span><span class="sxs-lookup"><span data-stu-id="5fac2-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="5fac2-159">обозначить существующую процедуру как автоматически запускаемую;</span><span class="sxs-lookup"><span data-stu-id="5fac2-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="5fac2-160">отменить выполнение процедуры при запуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fac2-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5fac2-161">безопасность</span><span class="sxs-lookup"><span data-stu-id="5fac2-161">Security</span></span>  
 <span data-ttu-id="5fac2-162">Дополнительные сведения см. в статьях [EXECUTE AS (Transact-SQL)](/sql/t-sql/statements/execute-as-transact-sql) и [EXECUTE AS Clause (Transact-SQL)](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fac2-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5fac2-163">Permissions</span><span class="sxs-lookup"><span data-stu-id="5fac2-163">Permissions</span></span>  
 <span data-ttu-id="5fac2-164">Дополнительные сведения см. в разделе "Разрешения" статьи [EXECUTE (Transact-SQL)](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fac2-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5fac2-165">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fac2-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="5fac2-166">Выполнение хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="5fac2-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="5fac2-167">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], разверните его, а затем разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="5fac2-168">Разверните нужную базу данных, разверните узлы **Программирование**и **Хранимые процедуры**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="5fac2-169">Щелкните правой кнопкой мыши определяемую пользователем хранимую процедуру и выберите команду **Выполнить хранимую процедуру**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="5fac2-170">В диалоговом окне **Выполнение процедуры** укажите значение для каждого параметра и необходимость передачи значения NULL.</span><span class="sxs-lookup"><span data-stu-id="5fac2-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="5fac2-171">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="5fac2-171">**Parameter**</span></span>  
     <span data-ttu-id="5fac2-172">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="5fac2-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="5fac2-173">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5fac2-173">**Data Type**</span></span>  
     <span data-ttu-id="5fac2-174">Указывает тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="5fac2-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="5fac2-175">**Выходной параметр**</span><span class="sxs-lookup"><span data-stu-id="5fac2-175">**Output Parameter**</span></span>  
     <span data-ttu-id="5fac2-176">Указывает, является ли этот параметр выходным.</span><span class="sxs-lookup"><span data-stu-id="5fac2-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="5fac2-177">**Передать значение NULL**</span><span class="sxs-lookup"><span data-stu-id="5fac2-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="5fac2-178">Передать значение NULL в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="5fac2-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="5fac2-179">**Значение**</span><span class="sxs-lookup"><span data-stu-id="5fac2-179">**Value**</span></span>  
     <span data-ttu-id="5fac2-180">Введите значение параметра, передаваемое ему при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="5fac2-181">Чтобы выполнить хранимую процедуру, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5fac2-182">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5fac2-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="5fac2-183">Выполнение хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="5fac2-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="5fac2-184">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fac2-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5fac2-185">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5fac2-186">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5fac2-187">В этом примере показано, как выполнить хранимую процедуру, которая принимает один параметр.</span><span class="sxs-lookup"><span data-stu-id="5fac2-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="5fac2-188">В примере выполняется хранимая процедура `uspGetEmployeeManagers` со значением  `6` , указанным в параметре `@EmployeeID` .</span><span class="sxs-lookup"><span data-stu-id="5fac2-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="5fac2-189">Установка и отмена автоматического запуска процедуры</span><span class="sxs-lookup"><span data-stu-id="5fac2-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="5fac2-190">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fac2-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5fac2-191">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5fac2-192">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5fac2-193">В этом примере показано, как использовать процедуру [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) , чтобы задать автоматическое выполнение процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="5fac2-194">Отмена автоматического выполнения процедуры</span><span class="sxs-lookup"><span data-stu-id="5fac2-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="5fac2-195">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fac2-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5fac2-196">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5fac2-197">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5fac2-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5fac2-198">В этом примере показано, как использовать процедуру [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) , чтобы отменить автоматическое выполнение процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fac2-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="5fac2-199">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5fac2-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fac2-200">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fac2-200">See Also</span></span>  
 <span data-ttu-id="5fac2-201">[Указание параметров](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="5fac2-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="5fac2-202">[Настройка параметра конфигураци и сервера scan for startup procs](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="5fac2-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="5fac2-203">[EXECUTE (Transact-SQL)](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5fac2-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="5fac2-204">[CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5fac2-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="5fac2-205">Хранимые процедуры (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="5fac2-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
