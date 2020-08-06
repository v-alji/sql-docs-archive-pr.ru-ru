---
title: Большие константы вводятся как типы больших значений в режиме совместимости 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655533"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="f5e8a-102">В режиме совместимости 90 и выше большие константы имеют тип больших значений</span><span class="sxs-lookup"><span data-stu-id="f5e8a-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="f5e8a-103">Помощник по обновлению обнаружил большие константы.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="f5e8a-104">Символьные строковые константы и двоичные константы размером более 8000 байт в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] рассматриваются как типы данных больших объектов.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="f5e8a-105">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях большие символьные и двоичные константы, а также константы в Юникоде, имеют тип больших значений.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f5e8a-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="f5e8a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f5e8a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f5e8a-107">Description</span></span>  
 <span data-ttu-id="f5e8a-108">Если строковые функции, например CHARINDEX или PATINDEX, используются со строковыми или двоичными константами размером более 8000 байт, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] возвращает ошибку с номером 8116, а [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздние версии — ошибку с номером 8152.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="f5e8a-109">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] строковые функции возвращают ошибку 8116, если они используются с `text` `ntext` типами данных, и `image` .</span><span class="sxs-lookup"><span data-stu-id="f5e8a-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="f5e8a-110">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях большие константы рассматриваются как типы данных `varchar(max)`, `nvarchar(max)` и `varbinary(max)` соответственно.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="f5e8a-111">Эти типы данных совместимы со строковыми функциями.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="f5e8a-112">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях строковые функции, такие как CHARINDEX и PATINDEX, предполагают, что размер найденной строки менее 8000 байт.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="f5e8a-113">Поэтому CHARINDEX и PATINDEX формируют ошибку 8152.</span><span class="sxs-lookup"><span data-stu-id="f5e8a-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e8a-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5e8a-114">See Also</span></span>  
 <span data-ttu-id="f5e8a-115">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f5e8a-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f5e8a-116">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="f5e8a-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
