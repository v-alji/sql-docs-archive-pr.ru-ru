---
title: MSSQLSERVER_10535 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731694"
---
# <a name="mssqlserver_10535"></a>MSSQLSERVER_10535
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|10535|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|PG_NO_PLAN|  
|Текст сообщения|Не удается создать структуру плана «%.*ls», поскольку план не найден в кэше планов, соответствующем указанному дескриптору плана. Укажите дескриптор плана в кэше. Список дескрипторов планов, находящихся в кэше, можно получить с помощью запроса к динамическому административному представлению sys.dm_exec_query_stats.|  
  
## <a name="explanation"></a>Объяснение  
 План не был найден в кэше планов, который соответствует указанному дескриптору плана.  
  
## <a name="user-action"></a>Действие пользователя  
 Укажите дескриптор плана в кэше. Список дескрипторов планов, находящихся в кэше, можно получить с помощью запроса к динамическому административному представлению sys.dm_exec_query_stats.  
  
## <a name="see-also"></a>См. также:  
 [sp_create_plan_guide_from_handle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)   
 [sys.dm_exec_query_stats (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
