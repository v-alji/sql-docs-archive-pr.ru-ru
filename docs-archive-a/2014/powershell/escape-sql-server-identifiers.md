---
title: Экранирование идентификаторов SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664277"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="88a04-102">Применение escape-символов к идентификаторам SQL Server</span><span class="sxs-lookup"><span data-stu-id="88a04-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="88a04-103">Часто можно использовать escape-символ обратной кавычки Windows PowerShell (\`) для экранирования символов, применение которых допускается в идентификаторах с разделителями [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , но не в именах путей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88a04-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="88a04-104">Тем не менее экранирование некоторых символов невозможно.</span><span class="sxs-lookup"><span data-stu-id="88a04-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="88a04-105">Например, в среде Windows PowerShell нельзя экранировать символ двоеточия (:).</span><span class="sxs-lookup"><span data-stu-id="88a04-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="88a04-106">Идентификаторы с этим символом должны быть закодированы.</span><span class="sxs-lookup"><span data-stu-id="88a04-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="88a04-107">Кодировка более надежна, чем экранирование, поскольку действует для всех символов.</span><span class="sxs-lookup"><span data-stu-id="88a04-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="88a04-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="88a04-108">Before You Begin</span></span>  
 <span data-ttu-id="88a04-109">Символ обратной кавычки (\`) обычно расположен на клавише в верхнем левом углу клавиатуры, под клавишей ESC.</span><span class="sxs-lookup"><span data-stu-id="88a04-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="88a04-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="88a04-110">Examples</span></span>  
 <span data-ttu-id="88a04-111">Ниже приведен пример экранирования символа #:</span><span class="sxs-lookup"><span data-stu-id="88a04-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="88a04-112">Это пример экранирования скобок при указании (local) в качестве имени компьютера:</span><span class="sxs-lookup"><span data-stu-id="88a04-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="88a04-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="88a04-113">See Also</span></span>  
 <span data-ttu-id="88a04-114">[SQL Server идентификаторов в PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="88a04-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="88a04-115">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="88a04-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="88a04-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="88a04-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
