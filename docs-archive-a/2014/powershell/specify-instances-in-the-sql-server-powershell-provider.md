---
title: Указание экземпляров в поставщике PowerShell (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658856"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="a0d8d-102">Указание экземпляров в поставщике SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0d8d-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="a0d8d-103">Пути, указанные для поставщика SQL Server для PowerShell, должны идентифицировать экземпляр компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] и компьютер, на котором он запущен.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="a0d8d-104">Синтаксическая конструкция для указания компьютера и экземпляра должна соответствовать правилам для идентификаторов SQL Server и путям Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="a0d8d-105">**Перед началом работы выполните следующие действия.**  [Ограничения](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="a0d8d-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="a0d8d-106">**Указание экземпляра:**  [Примеры](#Examples)</span><span class="sxs-lookup"><span data-stu-id="a0d8d-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a0d8d-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a0d8d-107">Before You Begin</span></span>  
 <span data-ttu-id="a0d8d-108">Первый узел, следующий за SQLSERVER:\SQL в пути поставщика SQL Server, является именем компьютера, на котором выполняется экземпляр компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], например:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="a0d8d-109">Если среда Windows PowerShell установлена на одном компьютере с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], то вместо имени компьютера можно использовать localhost или (local).</span><span class="sxs-lookup"><span data-stu-id="a0d8d-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="a0d8d-110">Скрипты, в которых указано localhost или (local), можно выполнять на любом компьютере, при этом изменять их путем внесения имен разных компьютеров не требуется.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="a0d8d-111">На одном и том же компьютере можно запустить несколько экземпляров исполняемой программы компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0d8d-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="a0d8d-112">Узел после имени компьютера в пути поставщика SQL Server определяет экземпляр, например:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="a0d8d-113">На каждом компьютере может быть только один экземпляр компонента [!INCLUDE[ssDE](../includes/ssde-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="a0d8d-114">При установке экземпляра по умолчанию указывать для него имя не нужно.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="a0d8d-115">При указании в строке соединения только имени компьютера происходит подключение к экземпляру по умолчанию на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="a0d8d-116">Все прочие экземпляры на компьютере должны быть именованными.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="a0d8d-117">Имя экземпляра указывается во время установки, а в строке подключения необходимо указывать и имя компьютера, и имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="a0d8d-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a0d8d-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a0d8d-119">Для указания локального компьютера в скриптах PowerShell нельзя использовать точку (.).</span><span class="sxs-lookup"><span data-stu-id="a0d8d-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="a0d8d-120">Точка не поддерживается, так как PowerShell интерпретирует точку как команду.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="a0d8d-121">Windows PowerShell обычно обрабатывает символы скобок в (local) как команды.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="a0d8d-122">Необходимо либо закодировать, либо экранировать их при использовании в пути, или заключить путь в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="a0d8d-123">Дополнительные сведения см. в разделе «Шифрование и расшифровка идентификаторов SQL Server».</span><span class="sxs-lookup"><span data-stu-id="a0d8d-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="a0d8d-124">Для поставщика [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] всегда необходимо указывать имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="a0d8d-125">Для экземпляров по умолчанию необходимо указывать имя DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a><span data-ttu-id="a0d8d-126">Примеров Имена компьютеров и экземпляров</span><span class="sxs-lookup"><span data-stu-id="a0d8d-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="a0d8d-127">В этом примере серверный объект устанавливается на экземпляр по умолчанию на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="a0d8d-128">Windows PowerShell обычно обрабатывает символы скобок в (local) как команды.</span><span class="sxs-lookup"><span data-stu-id="a0d8d-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="a0d8d-129">Необходимо:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-129">You must either:</span></span>  
  
-   <span data-ttu-id="a0d8d-130">заключить строку пути в кавычки;</span><span class="sxs-lookup"><span data-stu-id="a0d8d-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="a0d8d-131">экранировать скобки при помощи символа обратной кавычки (\`);</span><span class="sxs-lookup"><span data-stu-id="a0d8d-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="a0d8d-132">зашифровать скобки с помощью шестнадцатеричного представления:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0d8d-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0d8d-133">See Also</span></span>  
 <span data-ttu-id="a0d8d-134">[SQL Server идентификаторов в PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8d-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="a0d8d-135">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="a0d8d-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="a0d8d-136">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0d8d-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
