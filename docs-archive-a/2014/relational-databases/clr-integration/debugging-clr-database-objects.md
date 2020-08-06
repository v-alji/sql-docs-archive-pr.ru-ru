---
title: Отладка объектов базы данных CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654341"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="1372b-102">Отладка объектов базы данных среды CLR</span><span class="sxs-lookup"><span data-stu-id="1372b-102">Debugging CLR Database Objects</span></span>
  <span data-ttu-id="1372b-103">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предоставляется поддержка отладки объектов [!INCLUDE[tsql](../../../includes/tsql-md.md)] и среды CLR в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1372b-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="1372b-104">Ключевыми особенностями отладки в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] стали простота установки и использования, а также интеграция отладчика SQL Server с отладчиком Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1372b-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="1372b-105">Более того, процесс отладки охватывает код на всех применяемых языках:</span><span class="sxs-lookup"><span data-stu-id="1372b-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="1372b-106">пользователи могут беспрепятственно переходить к коду объектов среды CLR из кода [!INCLUDE[tsql](../../../includes/tsql-md.md)] и наоборот.</span><span class="sxs-lookup"><span data-stu-id="1372b-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="1372b-107">Отладчик Transact-SQL в среде SQL Server Management Studio нельзя использовать для отладки управляемых объектов базы данных, но эти объекты можно отлаживать с помощью отладчиков, входящих в состав среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1372b-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="1372b-108">Отладка управляемого объекта базы данных в Visual Studio поддерживает все обычные средства отладки, такие как шаг с входом и шаг с выходом в процедурах, выполняющихся на сервере.</span><span class="sxs-lookup"><span data-stu-id="1372b-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="1372b-109">Отладчики могут задавать точки останова, просматривать стек вызова, проверять значения переменных и изменять значения переменных во время отладки.</span><span class="sxs-lookup"><span data-stu-id="1372b-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="1372b-110">Обратите внимание, что среду Visual Studio .NET 2003 нельзя использовать для программирования или отладки в интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1372b-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> <span data-ttu-id="1372b-111">В состав [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] входит предварительно установленная платформа .NET Framework, а Visual Studio .NET 2003 не может использовать сборки .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="1372b-111">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="1372b-112">Дополнительные сведения об отладке управляемого кода с помощью Visual Studio см. в разделе "[Отладка управляемого кода](https://go.microsoft.com/fwlink/?LinkId=120377)" в документации по Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1372b-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="1372b-113">Разрешения и ограничения отладки</span><span class="sxs-lookup"><span data-stu-id="1372b-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="1372b-114">Отладка — это операция с высокой степенью привилегий, и поэтому в могут быть разрешены только члены предопределенной роли сервера **sysadmin** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1372b-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1372b-115">При отладке применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="1372b-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="1372b-116">При отладке процедур CLR можно использовать одновременно только один экземпляр отладчика.</span><span class="sxs-lookup"><span data-stu-id="1372b-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="1372b-117">Это ограничение налагается в связи с тем, что при достижении точки останова выполнение всего кода CLR приостанавливается и возобновляется лишь после прохождения отладчиком этой точки останова.</span><span class="sxs-lookup"><span data-stu-id="1372b-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="1372b-118">Однако отладку кода [!INCLUDE[tsql](../../../includes/tsql-md.md)] можно продолжать в других соединениях.</span><span class="sxs-lookup"><span data-stu-id="1372b-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="1372b-119">Хотя отладка кода [!INCLUDE[tsql](../../../includes/tsql-md.md)] не приводит к приостановке выполнения другого кода на сервере, она может вызывать переход других соединений в состояние ожидания в результате блокировки.</span><span class="sxs-lookup"><span data-stu-id="1372b-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="1372b-120">Отладка может быть выполнена только для новых соединений, так как перед выполнением соединения [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] требуются сведения о среде клиента и отладчика.</span><span class="sxs-lookup"><span data-stu-id="1372b-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="1372b-121">С учетом указанных ограничений рекомендуется отлаживать код [!INCLUDE[tsql](../../../includes/tsql-md.md)] и CLR на тестовом, а не на рабочем сервере.</span><span class="sxs-lookup"><span data-stu-id="1372b-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="1372b-122">Общие сведения об отладке управляемых объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="1372b-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="1372b-123">Отладка в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] организована на основе модели с учетом соединений.</span><span class="sxs-lookup"><span data-stu-id="1372b-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="1372b-124">Отладчик может обнаруживать и отлаживать действия только в том клиентском соединении, к которому он присоединен.</span><span class="sxs-lookup"><span data-stu-id="1372b-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="1372b-125">Функциональные возможности отладчика не ограничиваются типом соединения, поэтому возможна отладка как соединений с потоком табличных данных (TDS), так и HTTP-соединений.</span><span class="sxs-lookup"><span data-stu-id="1372b-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="1372b-126">Однако [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не позволяет выполнять отладку существующих соединений.</span><span class="sxs-lookup"><span data-stu-id="1372b-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="1372b-127">Процесс отладки поддерживает общие функции отладки внутри процедур, выполняемых на сервере.</span><span class="sxs-lookup"><span data-stu-id="1372b-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="1372b-128">Взаимодействие между отладчиком и сервером [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] происходит через модель DCOM.</span><span class="sxs-lookup"><span data-stu-id="1372b-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="1372b-129">Дополнительные сведения и сценарии отладки управляемых хранимых процедур, функций, триггеров, определяемых пользователем типов и статистических выражений см. в разделе "[SQL Server отладка базы данных интеграции со средой CLR](https://go.microsoft.com/fwlink/?LinkId=120378)" документации по Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1372b-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="1372b-130">Чтобы использовать Visual Studio для удаленной разработки, отладки и разработки, в экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] должен быть включен протокол TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="1372b-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="1372b-131">Дополнительные сведения о включении протокола TCP/IP на сервере см. в разделе [Настройка клиентских протоколов](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="1372b-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="1372b-132">Отладка управляемого объекта базы данных</span><span class="sxs-lookup"><span data-stu-id="1372b-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="1372b-133">Откройте среду Microsoft Visual Studio, создайте новый проект [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и установите соединение с базой данных экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1372b-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="1372b-134">Создайте новый тип.</span><span class="sxs-lookup"><span data-stu-id="1372b-134">Create a new type.</span></span> <span data-ttu-id="1372b-135">В **Обозреватель решений**щелкните правой кнопкой мыши проект, выберите **Добавить** и **новый элемент...** В окне **Добавление нового элемента** выберите **хранимая процедура**, **определяемая пользователем функция**, **определяемый пользователем тип**, **триггер**, **агрегат**или **класс**.</span><span class="sxs-lookup"><span data-stu-id="1372b-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="1372b-136">Укажите имя исходного файла нового типа и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1372b-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="1372b-137">Добавьте в текстовый редактор код для нового типа.</span><span class="sxs-lookup"><span data-stu-id="1372b-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="1372b-138">Образец кода для примера хранимой процедуры см. далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1372b-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="1372b-139">Добавьте скрипт, который будет тестировать этот тип.</span><span class="sxs-lookup"><span data-stu-id="1372b-139">Add a script that tests the type.</span></span> <span data-ttu-id="1372b-140">В **Обозреватель решений**разверните каталог **TestScripts** , дважды щелкните **Test. SQL** , чтобы открыть исходный файл скрипта теста по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1372b-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="1372b-141">Добавьте в текстовый редактор тестовый скрипт, вызывающий отладку кода.</span><span class="sxs-lookup"><span data-stu-id="1372b-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="1372b-142">Образец скрипта см. ниже.</span><span class="sxs-lookup"><span data-stu-id="1372b-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="1372b-143">Поместите одну или несколько точек останова в исходный код.</span><span class="sxs-lookup"><span data-stu-id="1372b-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="1372b-144">Щелкните правой кнопкой мыши строку кода в текстовом редакторе внутри функции или подпрограммы, которую необходимо отладить, и выберите **точка останова** и **Вставить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="1372b-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="1372b-145">Точка останова добавится, а строка кода будет выделена красным цветом.</span><span class="sxs-lookup"><span data-stu-id="1372b-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="1372b-146">В меню **Отладка** выберите команду **начать отладку** , чтобы скомпилировать, развернуть и протестировать проект.</span><span class="sxs-lookup"><span data-stu-id="1372b-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="1372b-147">В Test.sql запустится тестовый скрипт и будет вызван управляемый объект базы данных.</span><span class="sxs-lookup"><span data-stu-id="1372b-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="1372b-148">Когда на точке останова появится желтая стрелка, обозначающая указатель команд, выполнение кода приостановится и можно будет начать отладку управляемого объекта базы данных.</span><span class="sxs-lookup"><span data-stu-id="1372b-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="1372b-149">Вы можете **Перейти** в меню **Отладка** , чтобы переместить указатель инструкции на следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="1372b-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="1372b-150">Окно **локальные** используется для отслеживания состояния объектов, выделенных указателем инструкций.</span><span class="sxs-lookup"><span data-stu-id="1372b-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="1372b-151">Переменные можно добавить в окно **Контрольные значения** .</span><span class="sxs-lookup"><span data-stu-id="1372b-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="1372b-152">Состояние контролируемых переменных можно просмотреть по всему сеансу отладки, а не только в строке кода, выделенной указателем команд.</span><span class="sxs-lookup"><span data-stu-id="1372b-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="1372b-153">В меню «Отладка» нажмите кнопку «Продолжить», чтобы переместить указатель команд на следующую точку останова или завершить выполнение процедуры, если точек останова больше нет.</span><span class="sxs-lookup"><span data-stu-id="1372b-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1372b-154">Пример</span><span class="sxs-lookup"><span data-stu-id="1372b-154">Example</span></span>  
 <span data-ttu-id="1372b-155">Следующий пример возвращает версию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] участнику.</span><span class="sxs-lookup"><span data-stu-id="1372b-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="1372b-156">C#</span><span class="sxs-lookup"><span data-stu-id="1372b-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="1372b-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1372b-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1372b-158">Ниже представлен тестовый скрипт, вызывающий хранимую процедуру GetVersion, заданную выше.</span><span class="sxs-lookup"><span data-stu-id="1372b-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="1372b-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="1372b-159">See Also</span></span>  
 [<span data-ttu-id="1372b-160">Основные понятия о программировании интеграции со средой (CLR)</span><span class="sxs-lookup"><span data-stu-id="1372b-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
