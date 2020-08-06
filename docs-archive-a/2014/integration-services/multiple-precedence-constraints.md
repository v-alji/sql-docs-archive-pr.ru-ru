---
title: Несколько ограничений очередностью | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664315"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="1adf9-102">Множественные элементы управления очередностью</span><span class="sxs-lookup"><span data-stu-id="1adf9-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="1adf9-103">Объект управления очередностью соединяет два исполняемых объекта: две задачи, два контейнера или задачу и контейнер.</span><span class="sxs-lookup"><span data-stu-id="1adf9-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="1adf9-104">Они известны как приоритетный исполняемый объект и исполняемый объект с ограничением.</span><span class="sxs-lookup"><span data-stu-id="1adf9-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="1adf9-105">Исполняемый объект с ограничениями может иметь несколько элементов управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="1adf9-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="1adf9-106">Дополнительные сведения см. в статье [Precedence Constraints](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="1adf9-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="1adf9-107">Сборка сложных сценариев ограничений путем их группирования позволяет создавать сложный поток управления в пакетах.</span><span class="sxs-lookup"><span data-stu-id="1adf9-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="1adf9-108">Например, на следующей иллюстрации задача Г связана с задачей А ограничением `Success`, задача Г с задачей Б — ограничением `Failure`, а задачи Г и В — ограничением `Success`.</span><span class="sxs-lookup"><span data-stu-id="1adf9-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="1adf9-109">Элементы управления очередностью между задачами Г и А, между Г и Б, а также между Г и В участвуют в логических связях типа *and* .</span><span class="sxs-lookup"><span data-stu-id="1adf9-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="1adf9-110">Таким образом, для запуска задачи Г должна успешно запуститься задача А, аварийно завершиться задача Б и успешно запуститься задача В.</span><span class="sxs-lookup"><span data-stu-id="1adf9-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="1adf9-111">![Задачи, связанные ограничениями очередностью](media/precedenceconstraints.gif "Задачи, связанные ограничениями очередностью")</span><span class="sxs-lookup"><span data-stu-id="1adf9-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="1adf9-112">Свойство LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="1adf9-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="1adf9-113">Если задача или контейнер содержит несколько ограничений, то при помощи свойства `LogicalAnd` указывается, следует ли вычислять управление очередностью отдельно или вместе с остальными ограничениями.</span><span class="sxs-lookup"><span data-stu-id="1adf9-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="1adf9-114">Свойство можно задать `LogicalAnd` с помощью редактора управления **очередностью** в [!INCLUDE[ssIS](../includes/ssis-md.md)] конструкторе или в окно свойств, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] предоставляемой.</span><span class="sxs-lookup"><span data-stu-id="1adf9-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1adf9-115">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1adf9-115">Related Tasks</span></span>  
 [<span data-ttu-id="1adf9-116">Установка свойств управления очередностью</span><span class="sxs-lookup"><span data-stu-id="1adf9-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
