---
title: Вызов хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750856"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="8bbc9-102">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="8bbc9-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="8bbc9-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает как escape-последовательность ODBC CALL, так и [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкцию [EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) для выполнения хранимых процедур; в качестве предпочтительного метода используется escape-последовательность вызова ODBC.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="8bbc9-104">Использование синтаксиса ODBC позволяет приложению получать коды возврата хранимых процедур, а драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] оптимизирован в целях использования протокола, первоначально разработанного для отправки вызовов удаленных процедур (RPC) между компьютерами, на которых выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bbc9-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8bbc9-105">Этот протокол RPC повышает производительность, устраняя большую часть обработки параметров и синтаксической проверки инструкций на сервере.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bbc9-106">При вызове [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] хранимых процедур с использованием именованных параметров с помощью ODBC (Дополнительные сведения см. в разделе [Привязка параметров по имени (именованные параметры)](https://go.microsoft.com/fwlink/?LinkID=209721)). имена параметров должны начинаться с \@ символа "".</span><span class="sxs-lookup"><span data-stu-id="8bbc9-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="8bbc9-107">Это ограничение, характерное для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bbc9-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="8bbc9-108">В драйвере ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] это ограничение контролируется строже, чем в компонентах доступа к данным MDAC.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="8bbc9-109">Управляющая последовательность ODBC CALL для вызова процедуры такова:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="8bbc9-110">{[**? =**]**вызовите**_procedure_name_[([*параметр*] [**,**[*параметр*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="8bbc9-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="8bbc9-111">где *procedure_name* указывает имя процедуры, а *параметр* — параметр процедуры.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="8bbc9-112">Именованные параметры поддерживаются только в инструкциях, использующих escape-последовательности ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="8bbc9-113">Процедура может иметь параметры или не иметь их.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="8bbc9-114">Она также может возвращать значение (на что указывает необязательный маркер параметра «?=» в начале синтаксической конструкции).</span><span class="sxs-lookup"><span data-stu-id="8bbc9-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="8bbc9-115">Если параметр является входным или входным-выходным, то может представлять собой литерал или маркер параметра.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="8bbc9-116">Если параметр является выходным, то должен быть маркером параметра, поскольку выходной параметр неизвестен.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="8bbc9-117">Маркеры параметров должны быть привязаны к [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) перед выполнением инструкции вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="8bbc9-118">Входные и входные-выходные параметры в вызовах процедуры могут быть пропущены.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="8bbc9-119">Если процедура вызывается со скобками, но без параметров, то драйвер передает источнику данных указание, что для первого параметра должно использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="8bbc9-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-120">For example:</span></span>  
  
 <span data-ttu-id="8bbc9-121">{**call** _procedure_name_**()**}</span><span class="sxs-lookup"><span data-stu-id="8bbc9-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="8bbc9-122">Если процедура не имеет ни одного параметра, ее вызов завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="8bbc9-123">Если процедура вызывается без скобок, драйвер не передает какие-либо значения параметров.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="8bbc9-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-124">For example:</span></span>  
  
 <span data-ttu-id="8bbc9-125">{**call** _procedure_name_}</span><span class="sxs-lookup"><span data-stu-id="8bbc9-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="8bbc9-126">В вызовах процедур можно задавать литералы для входных или входных-выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="8bbc9-127">Например, процедура InsertOrder имеет пять входных параметров.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="8bbc9-128">В следующем вызове процедуры InsertOrder пропущен первый параметр, указан литерал для второго параметра и используется маркер параметра для третьего, четвертого и пятого параметра.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="8bbc9-129">(Параметры нумеруются последовательно, начиная с 1.)</span><span class="sxs-lookup"><span data-stu-id="8bbc9-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="8bbc9-130">Обратите внимание, что даже если параметр пропущен, запятая, отделяющая его от других параметров, должна присутствовать.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="8bbc9-131">Если пропущен входной или входной-выходной параметр, процедура использует значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="8bbc9-132">Другие способы задать значение по умолчанию для входного или входного-выходного параметра таковы: присвоить значение буфера длины и индикатора, привязанное к параметру процедуры SQL_DEFAULT_PARAM, или использовать ключевое слово DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="8bbc9-133">Если входной-выходной параметр пропущен или в качестве параметра выступает литерал, то драйвер отбрасывает выходное значение.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="8bbc9-134">Аналогичным образом, если пропущен маркер параметра для значения, возвращаемого процедурой, драйвер отбрасывает возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="8bbc9-135">Наконец, если в приложении задан параметр возвращаемого значения для процедуры, которая не возвращает значение, драйвер задает значение буфера длины и индикатора, привязанное к параметру процедуры SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="8bbc9-136">Разделители в инструкциях CALL</span><span class="sxs-lookup"><span data-stu-id="8bbc9-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="8bbc9-137">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию поддерживает также параметр совместимости для управляющей последовательности ODBC { CALL }.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="8bbc9-138">Он принимает инструкции CALL только с одним набором двойных кавычек, ограничивающих все имя хранимой процедуры:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="8bbc9-139">По умолчанию драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] принимает также инструкции CALL, которые соответствуют правилам ISO, и заключает каждый идентификатор в двойные кавычки:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="8bbc9-140">Но при выполнении с настройками по умолчанию драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает использование ни одной из форм представления идентификаторов, заключенных в кавычки, применительно к идентификаторам, которые содержат символы, не указанные как допустимые в стандарте ISO.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="8bbc9-141">Например, драйвер не может получить доступ к хранимой процедуре с именем **"My. proc"** с помощью инструкции Call с заключенными в кавычки идентификаторами:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="8bbc9-142">Эта инструкция интерпретируется драйвером следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="8bbc9-143">Сервер вызывает ошибку, связанную с тем, что связанный сервер с именем **myDB** не существует.</span><span class="sxs-lookup"><span data-stu-id="8bbc9-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="8bbc9-144">При использовании идентификаторов, заключенных в квадратные скобки, эта инструкция интерпретируется правильно:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bbc9-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bbc9-145">See Also</span></span>  
 [<span data-ttu-id="8bbc9-146">Выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="8bbc9-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
