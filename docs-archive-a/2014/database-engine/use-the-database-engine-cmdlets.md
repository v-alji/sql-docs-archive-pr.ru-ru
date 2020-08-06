---
title: Использование командлетов ядра СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655307"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="fae87-102">Использование командлетов компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="fae87-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="fae87-103">Командлеты Windows PowerShell представляют собой команды из одной функции, в именах которых, как правило, используется соглашение об именовании "глагол-существительное", например **Get-Help** или **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="fae87-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="fae87-104">Поставщик [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для Windows PowerShell предоставляет командлеты, относящиеся к [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fae87-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="fae87-105">Командлеты Database Engine</span><span class="sxs-lookup"><span data-stu-id="fae87-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="fae87-106">реализовано небольшое количество командлетов для компонента [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fae87-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="fae87-107">Эти командлеты в основном используются для запуска существующих скриптов Transact-SQL из новых скриптов PowerShell, оценки политик управления на основе политик и помощи в задании идентификаторов SQL Server в путях поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fae87-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="fae87-108">Большинство скриптов Windows PowerShell работают с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)] , используя поставщик SQL Server PowerShell и объектные модели управляемости SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fae87-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="fae87-109">Подробные сведения см. в статье [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fae87-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="fae87-110">Получение справки по командлету</span><span class="sxs-lookup"><span data-stu-id="fae87-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="fae87-111">В среде Windows PowerShell справочные сведения о каждом командлете можно получить с помощью командлета **Get-Help** .</span><span class="sxs-lookup"><span data-stu-id="fae87-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="fae87-112">Командлет**Get-Help** возвращает такую информацию, как синтаксис, определения параметров, типы входных и выходных данных, а также описание действий, выполняемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="fae87-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="fae87-113">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fae87-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="fae87-114">Частичные имена параметров</span><span class="sxs-lookup"><span data-stu-id="fae87-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="fae87-115">Полное имя параметра командлета указывать не обязательно.</span><span class="sxs-lookup"><span data-stu-id="fae87-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="fae87-116">Необходимо только указать достаточную часть имени, чтобы уникально отделить его от других параметров, поддерживаемых данным командлетом.</span><span class="sxs-lookup"><span data-stu-id="fae87-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="fae87-117">В следующих примерах показано три способа задания параметра **Invoke-Sqlcmd -QueryTimeout** :</span><span class="sxs-lookup"><span data-stu-id="fae87-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="fae87-118">Задачи командлета Database Engine</span><span class="sxs-lookup"><span data-stu-id="fae87-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="fae87-119">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="fae87-119">Task Description</span></span>|<span data-ttu-id="fae87-120">Раздел</span><span class="sxs-lookup"><span data-stu-id="fae87-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="fae87-121">Описывает использование командлета **Invoke-Sqlcmd** для выполнения скриптов **sqlcmd** или команд, содержащих инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] или XQuery.</span><span class="sxs-lookup"><span data-stu-id="fae87-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="fae87-122">Он может принимать входные данные **sqlcmd** в виде символьного строкового входного параметра или имени открываемого файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="fae87-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="fae87-123">Invoke-Sqlcmd, командлет</span><span class="sxs-lookup"><span data-stu-id="fae87-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="fae87-124">Описывает использование командлета **Invoke-PolicyEvaluation** для сообщения о том, соответствует ли целевой набор объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] условиям, определенным в схемах управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="fae87-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="fae87-125">Кроме того, этот командлет можно использовать для повторного задания любых настраиваемых параметров в целевых объектах, которые не соответствуют условиям политики.</span><span class="sxs-lookup"><span data-stu-id="fae87-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="fae87-126">Invoke-PolicyEvaluation, командлет</span><span class="sxs-lookup"><span data-stu-id="fae87-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="fae87-127">Описывает использование `Encode-Sqlname` и `Decode-Sqlname` для обработки идентификаторов SQL Server, содержащих символы, не поддерживаемые в путях Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fae87-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="fae87-128">Шифрование и расшифровка идентификаторов SQL Server</span><span class="sxs-lookup"><span data-stu-id="fae87-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="fae87-129">Описывает использование `Convert-UrnToPath` для преобразования универсального имени ресурса (URN) объекта управляемости SQL Server в эквивалентный путь поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fae87-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="fae87-130">Преобразование URNs в пути поставщика SQL Server</span><span class="sxs-lookup"><span data-stu-id="fae87-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="fae87-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="fae87-131">See Also</span></span>  
 <span data-ttu-id="fae87-132">[Поставщик SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="fae87-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="fae87-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="fae87-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="fae87-134">Общие сведения о командлетах PowerShell для группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fae87-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
