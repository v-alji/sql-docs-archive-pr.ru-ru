---
title: Создание хранимых процедур, скомпилированных в собственном коде | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657102"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="40369-102">Создание хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="40369-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="40369-103">Скомпилированные в собственном коде хранимые процедуры не реализуют полные возможности программирования [!INCLUDE[tsql](../../includes/tsql-md.md)] и контактную зону запросов.</span><span class="sxs-lookup"><span data-stu-id="40369-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="40369-104">Некоторые конструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] не могут быть использованы внутри хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="40369-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="40369-105">Дополнительные сведения см. [в разделе Поддерживаемые конструкции в хранимых процедурах, скомпилированных в собственном](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md)виде.</span><span class="sxs-lookup"><span data-stu-id="40369-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="40369-106">Однако некоторые функции [!INCLUDE[tsql](../../includes/tsql-md.md)] поддерживаются только для хранимых процедур, скомпилированных в собственном коде:</span><span class="sxs-lookup"><span data-stu-id="40369-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="40369-107">Блоки ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="40369-107">Atomic blocks.</span></span> <span data-ttu-id="40369-108">Дополнительные сведения см. в статье [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40369-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="40369-109">Ограничения `NOT NULL` на параметры и переменные в хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="40369-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="40369-110">Нельзя назначить значения `NULL` параметрам или переменным, объявленным как `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="40369-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="40369-111">Дополнительные сведения см. в статье [DECLARE @local_variable (Transact-SQL)](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40369-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="40369-112">Привязка к схеме хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="40369-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="40369-113">Скомпилированные в собственном коде хранимые процедуры создаются с помощью [CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40369-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="40369-114">В следующем примере показаны оптимизированная для памяти таблица и скомпилированная в собственном коде хранимая процедура, используемая для вставки строк в таблицу.</span><span class="sxs-lookup"><span data-stu-id="40369-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="40369-115">В образце кода `NATIVE_COMPILATION` указывает, что данная хранимая процедура [!INCLUDE[tsql](../../includes/tsql-md.md)] представляет собой хранимую процедуру, скомпилированную в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="40369-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="40369-116">Требуются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="40369-116">The following options are required:</span></span>  
  
|<span data-ttu-id="40369-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="40369-117">Option</span></span>|<span data-ttu-id="40369-118">Описание</span><span class="sxs-lookup"><span data-stu-id="40369-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="40369-119">Скомпилированная в собственном коде хранимая процедура должна быть привязана к схеме объектов, на которые она ссылается.</span><span class="sxs-lookup"><span data-stu-id="40369-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="40369-120">Это означает, что ссылки на таблицу со стороны процедуры не могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="40369-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="40369-121">Таблицы, на которые ссылается процедура, должны включать имя схемы, а подстановочные знаки ( \* ) не допускаются в запросах.</span><span class="sxs-lookup"><span data-stu-id="40369-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="40369-122">Параметр`SCHEMABINDING` поддерживается только для хранимых процедур, скомпилированных в собственном коде, в этой версии [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40369-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="40369-123">Хранимые процедуры, скомпилированные в собственном коде, не поддерживают `EXECUTE AS CALLER`, который является контекстом выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40369-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="40369-124">Поэтому необходимо указать контекст выполнения.</span><span class="sxs-lookup"><span data-stu-id="40369-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="40369-125">`EXECUTE AS OWNER`Поддерживаются параметры, `EXECUTE AS` *User*и `EXECUTE AS SELF` .</span><span class="sxs-lookup"><span data-stu-id="40369-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="40369-126">Тело хранимой процедуры, скомпилированной в собственном коде, должно представлять собой только один блок ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="40369-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="40369-127">Блоки ATOMIC гарантируют атомарное выполнение хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="40369-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="40369-128">Если процедура вызывается вне контекста активной транзакции, то запускает новую транзакцию, которая фиксируется после блока ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="40369-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="40369-129">Блоки ATOMIC в хранимых процедурах, скомпилированных в собственном коде, имеют два обязательных параметра:</span><span class="sxs-lookup"><span data-stu-id="40369-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="40369-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="40369-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="40369-131">См. раздел [уровни изоляции транзакций](../../database-engine/transaction-isolation-levels.md) для поддерживаемых уровней изоляции.</span><span class="sxs-lookup"><span data-stu-id="40369-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="40369-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="40369-132">`LANGUAGE`.</span></span> <span data-ttu-id="40369-133">Для хранимой процедуры необходимо назначить один из доступных языков или псевдонимов языка.</span><span class="sxs-lookup"><span data-stu-id="40369-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="40369-134">В случае `EXECUTE AS` и имени входа Windows ошибка может возникать из-за олицетворения с помощью `EXECUTE AS`.</span><span class="sxs-lookup"><span data-stu-id="40369-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="40369-135">Если пользовательская учетная запись использует проверку подлинности Windows, должно иметься полное доверие между учетной записью службы, используемой для экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], и доменом имени входа Windows.</span><span class="sxs-lookup"><span data-stu-id="40369-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="40369-136">Если полное доверие не установлено, при создании скомпилированной в собственном коде хранимой процедуры возвращается следующее сообщение об ошибке: MSG 15404. не удалось получить сведения о пользователе или группе Windows NT "Username", код ошибки 0x5.</span><span class="sxs-lookup"><span data-stu-id="40369-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="40369-137">Чтобы устранить эту неполадку, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="40369-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="40369-138">Используйте для службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] учетную запись из домена, к которому относится пользователь Windows.</span><span class="sxs-lookup"><span data-stu-id="40369-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="40369-139">Если [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует учетную запись компьютера, например Network Service или Local System, то домен, на котором находится пользователь Windows, должен иметь доверенную связь с компьютером.</span><span class="sxs-lookup"><span data-stu-id="40369-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="40369-140">Используйте проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40369-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="40369-141">При создании скомпилированной в собственном коде хранимой процедуры также можно видеть ошибку 15517.</span><span class="sxs-lookup"><span data-stu-id="40369-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="40369-142">Дополнительные сведения см. в разделе [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="40369-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="40369-143">Обновление хранимой процедуры, скомпилированной в собственном коде</span><span class="sxs-lookup"><span data-stu-id="40369-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="40369-144">Выполнение операций изменения для скомпилированных в собственном коде хранимых процедур не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="40369-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="40369-145">Один из способов изменения скомпилированной в собственном коде хранимой процедуры — ее удаление и повторное создание.</span><span class="sxs-lookup"><span data-stu-id="40369-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="40369-146">Создайте скрипт для разрешений на хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="40369-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="40369-147">Или же создайте скрипт для хранимой процедуры и сохраните в виде резервной копии.</span><span class="sxs-lookup"><span data-stu-id="40369-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="40369-148">Удалите хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="40369-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="40369-149">Создайте измененную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="40369-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="40369-150">Повторно примените разрешения на основе скрипта к хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="40369-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="40369-151">Недостаток данного подхода заключается в том, что приложение будет недоступно с начала выполнения шага 3 и до завершения шага 5.</span><span class="sxs-lookup"><span data-stu-id="40369-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="40369-152">Это может занять несколько секунд, и клиенту, использующему приложение, могут быть выданы сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="40369-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="40369-153">Другой способ эффективного изменения скомпилированной в собственном коде хранимой процедуры заключается в предварительном создании новой версии хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="40369-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="40369-154">В данном примере скомпилированная в собственном коде хранимая процедура имеет соответствующий номер версии.</span><span class="sxs-lookup"><span data-stu-id="40369-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="40369-155">Вызовем старую версию SP_Vold и новую версию SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="40369-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="40369-156">Сформируйте скрипт для разрешений на SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="40369-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="40369-157">Создайте SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="40369-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="40369-158">Примените разрешения SP_Vold в SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="40369-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="40369-159">Ссылки на SP_Vold обновите на SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="40369-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="40369-160">Для этого существует несколько способов, например:</span><span class="sxs-lookup"><span data-stu-id="40369-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="40369-161">Измените хранимую процедуру оболочки (на диске) так, чтобы она указывала на SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="40369-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="40369-162">Недостаток этого подхода заключается в ухудшении производительности из-за косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="40369-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="40369-163">Удалите SP_Vold (необязательно).</span><span class="sxs-lookup"><span data-stu-id="40369-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="40369-164">Преимущество этого подхода заключается в том, что приложение не переходит в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="40369-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="40369-165">Однако для поддержания ссылок и постоянного указания на последнюю версию хранимой процедуры требуются дополнительные усилия.</span><span class="sxs-lookup"><span data-stu-id="40369-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40369-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="40369-166">See Also</span></span>  
 [<span data-ttu-id="40369-167">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="40369-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
