---
title: Создание расширенных хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666614"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="b7acd-102">Создание расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="b7acd-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b7acd-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b7acd-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="b7acd-104">Расширенная хранимая процедура является функцией с прототипом:</span><span class="sxs-lookup"><span data-stu-id="b7acd-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="b7acd-105">Срвреткоде *xp_extendedProcName* **(** SRVPROC \*\* \* );\*\*</span><span class="sxs-lookup"><span data-stu-id="b7acd-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="b7acd-106">Указание префикса xp_ необязательно.</span><span class="sxs-lookup"><span data-stu-id="b7acd-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="b7acd-107">Имена расширенных хранимых процедур учитывают регистр символов, если на них ссылаются инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], независимо от установленной на сервере кодовой страницы и порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="b7acd-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="b7acd-108">При создании DLL-библиотеки нужно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="b7acd-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="b7acd-109">Если необходима точка входа, напишите функцию DllMain.</span><span class="sxs-lookup"><span data-stu-id="b7acd-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="b7acd-110">Эта функция необязательна. Если ее нет в исходном коде, то компилятор компонует собственную версию, которая всего лишь возвращает значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="b7acd-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="b7acd-111">Если функция DllMain создана, то операционная система вызывает ее в тот момент, когда поток или процесс присоединяется к DLL-библиотеке или отсоединяется от нее.</span><span class="sxs-lookup"><span data-stu-id="b7acd-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="b7acd-112">Все функции, которые вызываются за пределами DLL-библиотеки (все расширенные хранимые процедуры и функции), должны быть экспортированы.</span><span class="sxs-lookup"><span data-stu-id="b7acd-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="b7acd-113">Функцию можно экспортировать, перечисляя ее имя в разделе "ЭКСПОРТы" DEF-файла. также можно добавить префикс имени функции в исходный код с __declspec (dllexport), расширением компилятора Майкрософт (Обратите внимание, что \_ _declspec () начинается с двух символов подчеркивания).</span><span class="sxs-lookup"><span data-stu-id="b7acd-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="b7acd-114">Для создания DLL-библиотеки расширенной хранимой процедуры необходимы следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b7acd-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="b7acd-115">Файл</span><span class="sxs-lookup"><span data-stu-id="b7acd-115">File</span></span>|<span data-ttu-id="b7acd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b7acd-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b7acd-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="b7acd-117">Srv.h</span></span>|<span data-ttu-id="b7acd-118">Файл заголовка API-интерфейса расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="b7acd-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="b7acd-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="b7acd-119">Opends60.lib</span></span>|<span data-ttu-id="b7acd-120">Библиотека импорта для Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="b7acd-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="b7acd-121">Чтобы создать DLL-библиотеку расширенной хранимой процедуры, создайте проект типа «Динамическая библиотека».</span><span class="sxs-lookup"><span data-stu-id="b7acd-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="b7acd-122">Дополнительные сведения о создании DLL-библиотек см. в документации по среде разработки.</span><span class="sxs-lookup"><span data-stu-id="b7acd-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="b7acd-123">Настоятельно рекомендуется, чтобы все DLL-библиотеки расширенных хранимых процедур реализовали и экспортировали следующую функцию.</span><span class="sxs-lookup"><span data-stu-id="b7acd-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b7acd-124">Объявление __declspec(dllexport) является расширением компилятора Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b7acd-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="b7acd-125">Если компилятор не поддерживает эту директиву, то функцию необходимо экспортировать в DEF-файле в раздел EXPORTS.</span><span class="sxs-lookup"><span data-stu-id="b7acd-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="b7acd-126">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запускается с флагом трассировки-T260 или пользователь с правами системного администратора запускает инструкцию DBCC TRACEON (260), и если библиотека DLL расширенной хранимой процедуры не поддерживает __GetXpVersion (), то предупреждающее сообщение (ошибка 8131: DLL-библиотека расширенных хранимых процедур "%" не экспортирует \_ _GetXpVersion ().) в журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="b7acd-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="b7acd-127">(Обратите внимание, что \_ _GetXpVersion () начинается с двух знаков подчеркивания.)</span><span class="sxs-lookup"><span data-stu-id="b7acd-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="b7acd-128">Если DLL-библиотека расширенной хранимой процедуры экспортирует __GetXpVersion(), но версия, возвращенная этой функцией, меньше, чем требует сервер, то в журнал ошибок заносится предупредительное сообщение, содержащее версию, возвращенную функцией, и версию, ожидаемую сервером.</span><span class="sxs-lookup"><span data-stu-id="b7acd-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="b7acd-129">При получении этого сообщения возвращается неправильное значение из \_ _GetXpVersion () или компиляция выполняется с использованием более старой версии SRV. h.</span><span class="sxs-lookup"><span data-stu-id="b7acd-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7acd-130">Функция [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 SetErrorMode не должна вызываться в расширенных хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="b7acd-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="b7acd-131">Долго выполняющимся расширенным хранимым процедурам рекомендуется периодически вызывать функцию srv_got_attention, чтобы процедура могла завершиться при разрыве соединения или аварийного завершения пакетов.</span><span class="sxs-lookup"><span data-stu-id="b7acd-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="b7acd-132">Для отладки расширенной DLL-библиотеки хранимой процедуры скопируйте ее в каталог [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="b7acd-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="b7acd-133">Чтобы указать исполняемый файл для сеанса отладки, введите путь и имя [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] исполняемого файла (например, C:\PROGRAM Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span><span class="sxs-lookup"><span data-stu-id="b7acd-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="b7acd-134">Дополнительные сведения о аргументах sqlservr см. в разделе [приложение sqlservr](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="b7acd-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7acd-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7acd-135">See Also</span></span>  
 [<span data-ttu-id="b7acd-136">API srv_got_attention &#40;расширенных хранимых процедур&#41;</span><span class="sxs-lookup"><span data-stu-id="b7acd-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
