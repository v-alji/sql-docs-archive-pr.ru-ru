---
title: Шифрование и расшифровка идентификаторов SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729549"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="1be90-102">Шифрование и расшифровка идентификаторов SQL Server</span><span class="sxs-lookup"><span data-stu-id="1be90-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="1be90-103">Идентификаторы SQL Server с разделителями иногда содержат символы, не поддерживаемые в путях Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1be90-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="1be90-104">Эти символы можно задавать путем кодирования их шестнадцатеричных значений.</span><span class="sxs-lookup"><span data-stu-id="1be90-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="1be90-105">**Перед началом работы выполните следующие действия.**  [Ограничения](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="1be90-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="1be90-106">**Обработка специальных символов:**  [кодирование идентификатора](#EncodeIdent), [декодирование идентификатора](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="1be90-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1be90-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1be90-107">Before You Begin</span></span>  
 <span data-ttu-id="1be90-108">Символы, которые не поддерживаются в именах путей Windows PowerShell, могут быть представлены или закодированы как символ "%", за которым следует шестнадцатеричное значение для битового шаблона, представляющего символ, как в " **%** XX".</span><span class="sxs-lookup"><span data-stu-id="1be90-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="1be90-109">Для обработки символов, неподдерживаемых в обозначениях путей Windows PowerShell, всегда можно использовать кодировку.</span><span class="sxs-lookup"><span data-stu-id="1be90-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="1be90-110">Командлет **Encode-SqlName** принимает в качестве входных данных идентификатор [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1be90-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="1be90-111">Он возвращает строку, в которой все символы, не поддерживаемые языком Windows PowerShell, закодированы в виде «%xx».</span><span class="sxs-lookup"><span data-stu-id="1be90-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="1be90-112">Командлет **Decode-SqlName** принимает в качестве входных данных закодированный идентификатор [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и возвращает исходный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="1be90-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="1be90-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1be90-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1be90-114">Командлеты `Encode-Sqlname` и `Decode-Sqlname` обеспечивают только кодирование или декодирование символов, допустимых в идентификаторах SQL Server с разделителями, но не поддерживаемых в путях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1be90-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="1be90-115">Символы, кодируемые командлетом **Encode-SqlName** и декодируемые командлетом **Decode-SqlName**, перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="1be90-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="1be90-116">**Символ**</span><span class="sxs-lookup"><span data-stu-id="1be90-116">**Character**</span></span>|\ |/|<span data-ttu-id="1be90-117">:</span><span class="sxs-lookup"><span data-stu-id="1be90-117">:</span></span>|%|\<|>|*|<span data-ttu-id="1be90-118">?</span><span class="sxs-lookup"><span data-stu-id="1be90-118">?</span></span>|<span data-ttu-id="1be90-119">[</span><span class="sxs-lookup"><span data-stu-id="1be90-119">[</span></span>|<span data-ttu-id="1be90-120">]</span><span class="sxs-lookup"><span data-stu-id="1be90-120">]</span></span>|<span data-ttu-id="1be90-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="1be90-121">&#124;</span></span>|  
|<span data-ttu-id="1be90-122">**Шестнадцатеричная кодировка**</span><span class="sxs-lookup"><span data-stu-id="1be90-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="1be90-123">%5C</span><span class="sxs-lookup"><span data-stu-id="1be90-123">%5C</span></span>|<span data-ttu-id="1be90-124">%2F</span><span class="sxs-lookup"><span data-stu-id="1be90-124">%2F</span></span>|<span data-ttu-id="1be90-125">%3A</span><span class="sxs-lookup"><span data-stu-id="1be90-125">%3A</span></span>|<span data-ttu-id="1be90-126">%25</span><span class="sxs-lookup"><span data-stu-id="1be90-126">%25</span></span>|<span data-ttu-id="1be90-127">%3C</span><span class="sxs-lookup"><span data-stu-id="1be90-127">%3C</span></span>|<span data-ttu-id="1be90-128">%3E</span><span class="sxs-lookup"><span data-stu-id="1be90-128">%3E</span></span>|<span data-ttu-id="1be90-129">%2A</span><span class="sxs-lookup"><span data-stu-id="1be90-129">%2A</span></span>|<span data-ttu-id="1be90-130">%3F</span><span class="sxs-lookup"><span data-stu-id="1be90-130">%3F</span></span>|<span data-ttu-id="1be90-131">%5B</span><span class="sxs-lookup"><span data-stu-id="1be90-131">%5B</span></span>|<span data-ttu-id="1be90-132">%5D</span><span class="sxs-lookup"><span data-stu-id="1be90-132">%5D</span></span>|<span data-ttu-id="1be90-133">%7C</span><span class="sxs-lookup"><span data-stu-id="1be90-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a><span data-ttu-id="1be90-134">Кодирование идентификатора</span><span class="sxs-lookup"><span data-stu-id="1be90-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="1be90-135">**Кодирование идентификатора SQL Server в пути PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1be90-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="1be90-136">Используйте один из двух методов для кодирования идентификатора SQL Server:</span><span class="sxs-lookup"><span data-stu-id="1be90-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="1be90-137">Укажите шестнадцатеричный код для неподдерживаемого символа, используя синтаксис %XX, где XX — шестнадцатеричный код.</span><span class="sxs-lookup"><span data-stu-id="1be90-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="1be90-138">Передайте идентификатор в виде строки, заключенной в кавычки, в командлет `Encode-Sqlname`</span><span class="sxs-lookup"><span data-stu-id="1be90-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="1be90-139">Примеры (кодирование)</span><span class="sxs-lookup"><span data-stu-id="1be90-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="1be90-140">В этом примере указана закодированная версия символа «:» (%3A):</span><span class="sxs-lookup"><span data-stu-id="1be90-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="1be90-141">Можно также использовать **Encode-SqlName** для формирования имени, поддерживаемого Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1be90-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a> <span data-ttu-id="1be90-142">декодирование идентификатора</span><span class="sxs-lookup"><span data-stu-id="1be90-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="1be90-143">**Декодирование идентификатора SQL Server из пути PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1be90-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="1be90-144">Используйте командлет `Decode-Sqlname` для замены шестнадцатеричных кодов символами, представленными этими кодами.</span><span class="sxs-lookup"><span data-stu-id="1be90-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="1be90-145">Примеры (декодирование)</span><span class="sxs-lookup"><span data-stu-id="1be90-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="1be90-146">В этом примере происходит возврат строки Table:Test:</span><span class="sxs-lookup"><span data-stu-id="1be90-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="1be90-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="1be90-147">See Also</span></span>  
 <span data-ttu-id="1be90-148">[SQL Server идентификаторов в PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="1be90-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="1be90-149">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="1be90-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="1be90-150">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1be90-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
