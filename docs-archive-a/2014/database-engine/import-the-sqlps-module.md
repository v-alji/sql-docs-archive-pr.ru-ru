---
title: Импорт модуля SQLPS | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734445"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="20ce7-102">Импорт модуля SQLPS</span><span class="sxs-lookup"><span data-stu-id="20ce7-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="20ce7-103">Для управления [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из PowerShell рекомендуется импортировать модуль `sqlps` в среду Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="20ce7-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="20ce7-104">Модуль загружает и регистрирует оснастки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и сборки управляемости.</span><span class="sxs-lookup"><span data-stu-id="20ce7-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="20ce7-105">**Перед началом:**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="20ce7-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="20ce7-106">**Чтобы загрузить модуль:**  [Загрузка модуля sqlps](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="20ce7-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="20ce7-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="20ce7-107">Before You Begin</span></span>  
 <span data-ttu-id="20ce7-108">После импорта модуля `sqlps` в среду Windows PowerShell можно:</span><span class="sxs-lookup"><span data-stu-id="20ce7-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="20ce7-109">Вводить команды Windows PowerShell в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="20ce7-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="20ce7-110">Запускать файлы скриптов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ce7-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="20ce7-111">Запускать командлеты служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20ce7-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="20ce7-112">Использовать пути поставщика служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для передвижения по иерархии объектов среды служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20ce7-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="20ce7-113">Для управления объектами [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] используйте объектные модели управляемости [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (такие как Microsoft.SqlServer.Management.Smo).</span><span class="sxs-lookup"><span data-stu-id="20ce7-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20ce7-114">Команды, используемые в именах двух командлетов SQL Server (`Encode-Sqlname` и `Decode-Sqlname`), не соответствуют утвержденным командам для Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="20ce7-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="20ce7-115">Это не влияет на их работу, однако среда Windows PowerShell выдает предупреждение при импорте модуля `sqlps` в сеанс.</span><span class="sxs-lookup"><span data-stu-id="20ce7-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="20ce7-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="20ce7-116">Security</span></span>  
 <span data-ttu-id="20ce7-117">По умолчанию в Windows PowerShell политика выполнения скриптов работает в **ограниченном**режиме, блокируя все скрипты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ce7-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="20ce7-118">Для загрузки модуля `sqlps` можно использовать командлет `Set-ExecutionPolicy`, чтобы включить запуск как подписанных, так и любых других скриптов.</span><span class="sxs-lookup"><span data-stu-id="20ce7-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="20ce7-119">Следует выполнять только скрипты, полученные из доверенных источников, а также защищать все входные и выходные файлы, установив необходимые разрешения NTFS.</span><span class="sxs-lookup"><span data-stu-id="20ce7-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="20ce7-120">Дополнительные сведения о включении скриптов Windows PowerShell см. в разделе [Выполнение скриптов Windows PowerShell](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span><span class="sxs-lookup"><span data-stu-id="20ce7-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a> <span data-ttu-id="20ce7-121">Загрузка модуля sqlps</span><span class="sxs-lookup"><span data-stu-id="20ce7-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="20ce7-122">Загрузка модуля sqlps в среду Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20ce7-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="20ce7-123">Чтобы установить соответствующую политику выполнения скриптов, используйте командлет `Set-ExecutionPolicy`.</span><span class="sxs-lookup"><span data-stu-id="20ce7-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="20ce7-124">Для импорта модуля sqlps используйте командлет `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="20ce7-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="20ce7-125">Если требуется отключить предупреждение о `DisableNameChecking` и `Encode-Sqlname`, задайте параметр `Decode-Sqlname`.</span><span class="sxs-lookup"><span data-stu-id="20ce7-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="20ce7-126">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="20ce7-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="20ce7-127">В этом примере показана загрузка модуля `sqlps` с отключенной проверкой имен.</span><span class="sxs-lookup"><span data-stu-id="20ce7-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="20ce7-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="20ce7-128">See Also</span></span>  
 <span data-ttu-id="20ce7-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="20ce7-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="20ce7-130">[Поставщик SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="20ce7-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="20ce7-131">Использование командлетов компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="20ce7-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
