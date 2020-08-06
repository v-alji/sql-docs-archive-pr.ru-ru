---
title: Объект SqlTriggerContext | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751208"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="3c151-102">SqlTriggerContext, объект</span><span class="sxs-lookup"><span data-stu-id="3c151-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="3c151-103">Класс `SqlTriggerContext` предоставляет сведения контекста о триггере.</span><span class="sxs-lookup"><span data-stu-id="3c151-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="3c151-104">В сведения о контексте включают тип действия, вызвавшего срабатывание триггера, столбцы, измененные в рамках операции UPDATE, а в случае триггера DDL — структуру XML `EventData`, которая описывает операцию триггера.</span><span class="sxs-lookup"><span data-stu-id="3c151-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="3c151-105">Дополнительные сведения и примеры использования `SqlTriggerContext` класса см. в разделе [триггеры CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="3c151-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="3c151-106">Дополнительные сведения см. в справочной документации по классу `Microsoft.SqlServer.Server.SqlTriggerContext` в документации по пакету .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="3c151-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c151-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c151-107">See Also</span></span>  
 <span data-ttu-id="3c151-108">[Триггеры CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="3c151-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="3c151-109">EVENTDATA (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3c151-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
