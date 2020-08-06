---
title: Добавление расширенной хранимой процедуры в SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666616"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="580c0-102">Добавление на SQL Server расширенной хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="580c0-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="580c0-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="580c0-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="580c0-104">DLL-библиотека, которая содержит функции расширенных хранимых процедур, используется как расширение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="580c0-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="580c0-105">Чтобы установить библиотеку DLL, скопируйте файл в каталог, например в тот, который содержит стандартные [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файлы DLL (C:\Program FILES\MICROSOFT SQL Server\MSSQL12.0.\* x\*\MSSQL\Binn по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="580c0-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="580c0-106">После копирования DLL-библиотеки расширенной хранимой процедуры на сервер, системному администратору [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] следует зарегистрировать в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] каждую из функций расширенной хранимой процедуры в DLL-библиотеке.</span><span class="sxs-lookup"><span data-stu-id="580c0-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="580c0-107">Это выполняется с помощью системной хранимой процедуры sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="580c0-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="580c0-108">Перед добавлением расширенной процедуры на сервер и предоставлением разрешения на ее выполнение другим пользователям системному администратору следует тщательно проверить расширенную хранимую процедуру, чтобы убедиться, что она не содержит вредоносного или злонамеренного кода.</span><span class="sxs-lookup"><span data-stu-id="580c0-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="580c0-109">Проверяйте все данные, вводимые пользователем.</span><span class="sxs-lookup"><span data-stu-id="580c0-109">Validate all user input.</span></span> <span data-ttu-id="580c0-110">Не осуществляйте объединение пользовательских входных данных до их проверки.</span><span class="sxs-lookup"><span data-stu-id="580c0-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="580c0-111">Никогда не выполняйте команду, построенную на основании непроверенных пользовательских входных данных.</span><span class="sxs-lookup"><span data-stu-id="580c0-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="580c0-112">Первый параметр sp_addextendedproc указывает имя функции, а второй параметр указывает имя DLL-библиотеки, в которой размещается функция.</span><span class="sxs-lookup"><span data-stu-id="580c0-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="580c0-113">Рекомендуется указывать полный путь DLL.</span><span class="sxs-lookup"><span data-stu-id="580c0-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="580c0-114">Существующие библиотеки DLL, которые не зарегистрированы с полным путем, перестанут работать после обновления до SQL Server 2005 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="580c0-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="580c0-115">Для решения этой проблемы воспользуйтесь хранимой процедурой sp_dropextendedproc для отмены регистрации DLL-библиотеки, а затем выполните их повторную регистрацию процедурой sp_addextendedproc, указывая полный путь доступа.</span><span class="sxs-lookup"><span data-stu-id="580c0-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="580c0-116">Имя функции, передаваемое хранимой процедуре `sp_addextendedproc`, должно полностью совпадать с именем функции в DLL-библиотеке, включая регистр символов.</span><span class="sxs-lookup"><span data-stu-id="580c0-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="580c0-117">Например, следующая команда регистрирует функцию `xp_hello,`, расположенную в DLL-библиотеке с именем `xp_hello.dll`, в качестве расширенной хранимой процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="580c0-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="580c0-118">Если имя функции, указанное в процедуре `sp_addextendedproc`, не соответствует в точности имени функции в DLL-библиотеке, новое имя будет зарегистрировано в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но это имя будет непригодно для использования.</span><span class="sxs-lookup"><span data-stu-id="580c0-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="580c0-119">Например, хотя `xp_Hello` регистрируется как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Расширенная хранимая процедура, расположенная в `xp_hello.dll` , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не сможет найти функцию в библиотеке DLL, если вы используете `xp_Hello` для вызова функции позже.</span><span class="sxs-lookup"><span data-stu-id="580c0-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="580c0-120">Если имя функции, указанное в `sp_addextendedproc`, точно соответствует имени функции в DLL-библиотеке, а в параметрах сортировки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не учитывается регистр, пользователь может вызвать расширенную хранимую процедуру с использованием любого сочетания символов нижнего и верхнего регистров в ее имени.</span><span class="sxs-lookup"><span data-stu-id="580c0-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="580c0-121">Если в параметрах сортировки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учитывается регистр, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не сможет вызвать расширенную хранимую процедуру, даже если она была зарегистрирована точно с тем же именем и параметрами сортировки, как функция в DLL-библиотеке, если при вызове процедуры ее имя указано в другом регистре символов.</span><span class="sxs-lookup"><span data-stu-id="580c0-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="580c0-122">Останавливать и перезапускать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не обязательно.</span><span class="sxs-lookup"><span data-stu-id="580c0-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580c0-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="580c0-123">See Also</span></span>  
 <span data-ttu-id="580c0-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="580c0-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="580c0-125">sp_dropextendedproc (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="580c0-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
