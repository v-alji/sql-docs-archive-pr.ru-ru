---
title: Преобразование универсальных имен ресурса в пути поставщика SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664485"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="d43cf-102">Преобразование универсальных имен ресурса в пути поставщика SQL Server</span><span class="sxs-lookup"><span data-stu-id="d43cf-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="d43cf-103">Модель объектов управления [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] создает унифицированные имена ресурсов (URN) для своих объектов.</span><span class="sxs-lookup"><span data-stu-id="d43cf-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="d43cf-104">Каждое универсальное имя ресурса (URN) однозначно определяет объект SMO и может быть преобразовано в путь поставщика SQL Server PowerShell с помощью командлета `Convert-UrnToPath`.</span><span class="sxs-lookup"><span data-stu-id="d43cf-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="d43cf-105">Преобразование имен URN в пути</span><span class="sxs-lookup"><span data-stu-id="d43cf-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="d43cf-106">Каждое имя URN содержит ту же информацию, что и путь к объекту, но представленную в другой форме.</span><span class="sxs-lookup"><span data-stu-id="d43cf-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="d43cf-107">Например, ниже показан путь к таблице:</span><span class="sxs-lookup"><span data-stu-id="d43cf-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="d43cf-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="d43cf-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="d43cf-109">А ниже приведено имя URN, указывающее на тот же объект:</span><span class="sxs-lookup"><span data-stu-id="d43cf-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="d43cf-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="d43cf-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="d43cf-111">Если объект SMO создан в скрипте PowerShell, можно узнать универсальное имя ресурса объекта из свойства `Urn`, а затем использовать командлет `Convert-UrnToPath` для преобразования строки универсального имени ресурса объекта SMO в путь Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d43cf-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="d43cf-112">Затем можно использовать поставщик для перехода в различные точки на пути.</span><span class="sxs-lookup"><span data-stu-id="d43cf-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="d43cf-113">Если имена узлов содержат дополнительные символы, которые не поддерживаются в именах путей Windows PowerShell, командлет `Convert-UrnToPath` преобразует их в шестнадцатеричное представление.</span><span class="sxs-lookup"><span data-stu-id="d43cf-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="d43cf-114">Например, строка «My:Table» возвращается как «My%3ATable».</span><span class="sxs-lookup"><span data-stu-id="d43cf-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="d43cf-115">Чтобы ознакомиться с примерами использования этого командлета, выполните в среде Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d43cf-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="d43cf-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d43cf-116">See Also</span></span>  
 <span data-ttu-id="d43cf-117">[Выражения запросов и универсальные имена ресурсов](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="d43cf-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="d43cf-118">[Поставщик SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d43cf-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="d43cf-119">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="d43cf-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
