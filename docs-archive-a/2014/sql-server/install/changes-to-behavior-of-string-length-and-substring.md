---
title: Изменения в поведении строковой длины и подстроки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659229"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="5183b-102">Изменения в работе функций длины строки и подстроки</span><span class="sxs-lookup"><span data-stu-id="5183b-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="5183b-103">[Функция строкового размера &#40;xquery&#41;](/sql/xquery/functions-on-string-values-string-length) и [Функция SUBSTRING &#40;функции XQuery&#41;](/sql/xquery/functions-on-string-values-substring) могут возвращать различные результаты при использовании с базами данных XML, содержащими суррогатные символы.</span><span class="sxs-lookup"><span data-stu-id="5183b-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5183b-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5183b-104">Description</span></span>  
 <span data-ttu-id="5183b-105">Если база данных настроена для совместимости с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , поведение [функции строки, &#40;&#41;XQuery](/sql/xquery/functions-on-string-values-string-length) и [функция substring &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) функции, изменяются при работе с дополнительными символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="5183b-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="5183b-106">Каждый дополнительный символ Юникода, определяемый по кодовой точке больше чем U+FFFF, считается в этих функциях одним символом, а не двумя, как было в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="5183b-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="5183b-107">Дополнительные сведения о суррогатных символах см. в разделе [Суррогаты и дополнительные символы](https://go.microsoft.com/fwlink/?LinkId=178317).</span><span class="sxs-lookup"><span data-stu-id="5183b-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5183b-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="5183b-108">See Also</span></span>  
 <span data-ttu-id="5183b-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5183b-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="5183b-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="5183b-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
