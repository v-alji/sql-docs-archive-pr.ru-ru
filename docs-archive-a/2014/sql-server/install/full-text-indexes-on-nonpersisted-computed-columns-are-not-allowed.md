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
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a>Полнотекстовые индексы для нематериализованных вычисляемых столбцов недопустимы
  Нельзя создавать полнотекстовые индексы на основе недетерминированных и неточных вычисляемых столбцов. Такие столбцы не могут использоваться ни как типизированные, ни в качестве полнотекстовых ключевых столбцов.  
  
## <a name="description"></a>Описание  
 В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] полнотекстовый индекс может быть создан с использованием недетерминированных и неточных вычисляемых столбцов в качестве столбцов типа или полнотекстовых ключевых столбцов. Эта функциональность не поддерживается. При обновлении более старые, несовместимые и неподдерживаемые полнотекстовые индексы отключаются.  
  
## <a name="corrective-action"></a>Действие по исправлению  
 Чтобы включить эти полнотекстовые индексы, измените определения столбцов так, чтобы они стали детерминированными и точными.  
  
## <a name="see-also"></a>См. также:  
 [Работа с помощником по обновлению](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
