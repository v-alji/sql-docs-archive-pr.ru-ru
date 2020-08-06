---
title: MSSQLSERVER_ 10536 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734126"
---
# <a name="mssqlserver_10536"></a>MSSQLSERVER_10536
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|10536|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|PG_TOO_MANY_STMTS|  
|Текст сообщения|Не удалось создать структуру плана "%.\*ls", поскольку пакет или модуль, соответствующий указанному параметру `@plan_handle`, содержит более 1000 подходящих инструкций. Создайте структуру плана для каждой инструкции в пакете или модуле, указав для каждой инструкции значение `statement_start_offset`.|  
  
## <a name="explanation"></a>Объяснение  
 Пакет или модуль, соответствующий указанному дескриптору `@plan_handle`, содержит больше 1000 подходящих инструкций.  
  
## <a name="user-action"></a>Действие пользователя  
 Создайте структуру плана для каждой инструкции в пакете или модуле, указав для каждой инструкции значение `statement_start_offset`.  
  
## <a name="see-also"></a>См. также:  
 [sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)   
 [Структуры планов](../performance/plan-guides.md)   
 [sp_create_plan_guide_from_handle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
