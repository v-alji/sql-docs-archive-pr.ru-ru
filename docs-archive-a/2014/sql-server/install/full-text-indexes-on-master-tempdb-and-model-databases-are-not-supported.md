---
title: Полнотекстовые индексы баз данных master, tempdb и Model не поддерживаются | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669262"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="04ec8-102">Полнотекстовые индексы в базах данных master, tempdb и model не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="04ec8-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04ec8-103">не позволяет создавать полнотекстовые индексы для системных баз данных.</span><span class="sxs-lookup"><span data-stu-id="04ec8-103">does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="04ec8-104">Описание</span><span class="sxs-lookup"><span data-stu-id="04ec8-104">Description</span></span>  
 <span data-ttu-id="04ec8-105">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] полнотекстовые индексы поддерживались в базах данных master, tempdb и model.</span><span class="sxs-lookup"><span data-stu-id="04ec8-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="04ec8-106">Все полнотекстовые каталоги в базах данных master, tempdb и Model удаляются во время обновления.</span><span class="sxs-lookup"><span data-stu-id="04ec8-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ec8-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="04ec8-107">See Also</span></span>  
 [<span data-ttu-id="04ec8-108">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="04ec8-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
