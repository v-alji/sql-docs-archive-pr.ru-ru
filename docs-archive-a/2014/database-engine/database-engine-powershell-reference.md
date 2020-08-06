---
title: Справочник по PowerShell для ядра СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665102"
---
# <a name="database-engine-powershell-reference"></a><span data-ttu-id="da0ad-102">Справочник по PowerShell для ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="da0ad-102">Database Engine PowerShell Reference</span></span>
  <span data-ttu-id="da0ad-103">В состав [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] включен набор командлетов Windows PowerShell 2.0 для выполнения обычных действий в компоненте [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da0ad-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] includes a set of Windows PowerShell 2.0 cmdlets for performing common actions in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="da0ad-104">Кроме того, выражения запросов и универсальные имена ресурса (URN) можно преобразовать в пути SQL Server PowerShell либо использовать для указания одного или нескольких объектов в компоненте [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da0ad-104">In addition, Query Expressions and Uniform Resource Names (URN) can be converted to SQL Server PowerShell paths, or used to specify one or more objects in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="da0ad-105">Командлеты Database Engine</span><span class="sxs-lookup"><span data-stu-id="da0ad-105">Database Engine Cmdlets</span></span>  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] <span data-ttu-id="da0ad-106">включает в себя сравнительно мало командлетов для компонента [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da0ad-106">includes relatively few cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="da0ad-107">Большинство скриптов Windows PowerShell, работающих с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)] , используют поставщика SQL Server PowerShell и объектные модели управляемости SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da0ad-107">Most PowerShell scripts working with the [!INCLUDE[ssDE](../includes/ssde-md.md)] use the SQL Server PowerShell provider and the manageability object models.</span></span> <span data-ttu-id="da0ad-108">Дополнительные сведения см. в статье [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="da0ad-108">For more information, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
 <span data-ttu-id="da0ad-109">Описание получения справки о командлетах SQL Server в среде Windows PowerShell см. в разделе [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="da0ad-109">To learn how to get help about the SQL Server cmdlets in a Windows PowerShell environment, see [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="da0ad-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="da0ad-110">In This Section</span></span>  
 <span data-ttu-id="da0ad-111">В данном разделе содержатся сведения об этих командлетах.</span><span class="sxs-lookup"><span data-stu-id="da0ad-111">This section contains information about these cmdlets.</span></span>  
  
|<span data-ttu-id="da0ad-112">Описание</span><span class="sxs-lookup"><span data-stu-id="da0ad-112">Description</span></span>|<span data-ttu-id="da0ad-113">Командлет</span><span class="sxs-lookup"><span data-stu-id="da0ad-113">Cmdlet</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="da0ad-114">Выполняет скрипты Transact-SQL и XQuery, например скрипты, которые можно выполнить с помощью программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="da0ad-114">Runs Transact-SQL and XQuery scripts, such as scripts that can be run using the `sqlcmd` utility.</span></span>|[<span data-ttu-id="da0ad-115">Invoke-Sqlcmd, командлет</span><span class="sxs-lookup"><span data-stu-id="da0ad-115">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="da0ad-116">Определяет, соответствует ли объект компонента Database Engine политике управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="da0ad-116">Evaluates whether a Database Engine object complies with a Policy-based Management policy.</span></span>|[<span data-ttu-id="da0ad-117">Invoke-PolicyEvaluation, командлет</span><span class="sxs-lookup"><span data-stu-id="da0ad-117">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a><span data-ttu-id="da0ad-118">Сведения о других командлетах</span><span class="sxs-lookup"><span data-stu-id="da0ad-118">Information About Other Cmdlets</span></span>  
 <span data-ttu-id="da0ad-119">Командлеты `Encode-Sqlname` и `Decode-Sqlname` помогают указать идентификаторы SQL Server, содержащие символы, не поддерживаемые в путях Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da0ad-119">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets help you specify SQL Server identifiers that contain characters not supported in PowerShell paths.</span></span> <span data-ttu-id="da0ad-120">Дополнительные сведения см. в статье [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="da0ad-120">For more information, see [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span></span>  
  
 <span data-ttu-id="da0ad-121">Используйте командлет `Convert-UrnToPath`, чтобы преобразовать уникальное имя ресурса для объекта компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] в путь для поставщика SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da0ad-121">Use the `Convert-UrnToPath` cmdlet to convert a Unique Resource Name for a [!INCLUDE[ssDE](../includes/ssde-md.md)] object to a path for the SQL Server PowerShell provider.</span></span> <span data-ttu-id="da0ad-122">Дополнительные сведения см. в статье [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span><span class="sxs-lookup"><span data-stu-id="da0ad-122">For more information, see [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span></span>  
  
## <a name="query-expressions-and-unique-resource-names"></a><span data-ttu-id="da0ad-123">Выражения запросов и уникальные имена ресурсов</span><span class="sxs-lookup"><span data-stu-id="da0ad-123">Query Expressions and Unique Resource Names</span></span>  
 <span data-ttu-id="da0ad-124">Выражения запроса — это строки, которые используют синтаксис, напоминающий XPath для указания набора условий, перечисляющих один или несколько объектов в иерархии объектной модели.</span><span class="sxs-lookup"><span data-stu-id="da0ad-124">Query expressions are strings that use syntax similar to XPath to specify a set of criteria that enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="da0ad-125">Уникальное имя ресурса (URN) — это определенный тип строки выражения запроса, который уникально определяет один объект.</span><span class="sxs-lookup"><span data-stu-id="da0ad-125">A Unique Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span> <span data-ttu-id="da0ad-126">Дополнительные сведения см. в статье [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="da0ad-126">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da0ad-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="da0ad-127">See Also</span></span>  
 [<span data-ttu-id="da0ad-128">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="da0ad-128">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
  
  
