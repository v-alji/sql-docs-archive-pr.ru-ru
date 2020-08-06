---
title: Средство разбиения текста на слова и фильтры для полнотекстового поиска значительно улучшилось в SQL Server 2005 и SQL Server 2008 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 8d06bda9-0bbf-4baa-b270-07b1c1f640eb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d2e7d3b8da56b407d3937b05cd980c3f8a4eb0c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668070"
---
# <a name="full-text-search-word-breakers-and-filters-significantly-improved-in-sql-server-2005-and-sql-server-2008"></a><span data-ttu-id="9db44-102">В SQL Server 2005 и SQL Server 2008 средства разбиения по словам и фильтры полнотекстового поиска были существенно улучшены</span><span class="sxs-lookup"><span data-stu-id="9db44-102">Full-Text Search word breakers and filters significantly improved in SQL Server 2005 and SQL Server 2008</span></span>
  <span data-ttu-id="9db44-103">Средства разбиения по словам и фильтры значительно изменились.</span><span class="sxs-lookup"><span data-stu-id="9db44-103">The word breakers and filters were significantly changed.</span></span> <span data-ttu-id="9db44-104">Были дополнительно улучшены средства разбиения по словам, включая улучшенную поддержку языков и надежность.</span><span class="sxs-lookup"><span data-stu-id="9db44-104">Additional improvements have been made to word breakers, including enhanced language coverage and reliability.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9db44-105">Описание</span><span class="sxs-lookup"><span data-stu-id="9db44-105">Description</span></span>  
 <span data-ttu-id="9db44-106">Средства разбиения по словам и фильтры, используемые полнотекстовым поиском [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], были значительно изменены для улучшения функциональности и надежности.</span><span class="sxs-lookup"><span data-stu-id="9db44-106">Word breakers and filters used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Full-Text Search have been significantly modified to achieve improvements in functionality and reliability.</span></span> <span data-ttu-id="9db44-107">В некоторых конкретных случаях изменения в средстве разбиения по словам могут повлиять на то, как размечаются некоторые данные.</span><span class="sxs-lookup"><span data-stu-id="9db44-107">In some specific cases, changes to the word breakers can impact how some data is tokenized.</span></span> <span data-ttu-id="9db44-108">Токены, создаваемые в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], могут отличаться от токенов более ранней версии, созданных в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] или [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9db44-108">Tokens created in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] may be different from earlier tokens created in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="9db44-109">Дополнительные сведения о средстве разбиения по словам см. в разделе [Настройка и Управление разделителями слов и парадигматические модули для поиска](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="9db44-109">For information about word breakers, see [Configure and Manage Word Breakers and Stemmers for Search](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db44-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="9db44-110">See Also</span></span>  
 [<span data-ttu-id="9db44-111">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="9db44-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
