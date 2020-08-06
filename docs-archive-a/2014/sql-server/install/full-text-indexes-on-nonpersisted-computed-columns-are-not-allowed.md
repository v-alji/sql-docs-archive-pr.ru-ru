---
title: Полнотекстовые индексы для нематериализованных, рассчитанных столбцов не допускаются | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669261"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="0ac06-102">Полнотекстовые индексы для нематериализованных вычисляемых столбцов недопустимы</span><span class="sxs-lookup"><span data-stu-id="0ac06-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="0ac06-103">Нельзя создавать полнотекстовые индексы на основе недетерминированных и неточных вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="0ac06-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="0ac06-104">Такие столбцы не могут использоваться ни как типизированные, ни в качестве полнотекстовых ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="0ac06-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0ac06-105">Описание</span><span class="sxs-lookup"><span data-stu-id="0ac06-105">Description</span></span>  
 <span data-ttu-id="0ac06-106">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] полнотекстовый индекс может быть создан с использованием недетерминированных и неточных вычисляемых столбцов в качестве столбцов типа или полнотекстовых ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="0ac06-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="0ac06-107">Эта функциональность не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0ac06-107">This functionality is not supported.</span></span> <span data-ttu-id="0ac06-108">При обновлении более старые, несовместимые и неподдерживаемые полнотекстовые индексы отключаются.</span><span class="sxs-lookup"><span data-stu-id="0ac06-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0ac06-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="0ac06-109">Corrective Action</span></span>  
 <span data-ttu-id="0ac06-110">Чтобы включить эти полнотекстовые индексы, измените определения столбцов так, чтобы они стали детерминированными и точными.</span><span class="sxs-lookup"><span data-stu-id="0ac06-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac06-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ac06-111">See Also</span></span>  
 [<span data-ttu-id="0ac06-112">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="0ac06-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
