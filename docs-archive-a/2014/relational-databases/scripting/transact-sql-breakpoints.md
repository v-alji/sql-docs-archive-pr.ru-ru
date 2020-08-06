---
title: Точки останова Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667015"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="c98fd-102">Точки останова Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c98fd-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="c98fd-103">Точка останова указывает, что отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] приостанавливает выполнение на конкретной инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , после чего можно просмотреть состояние элементов кода на данном этапе.</span><span class="sxs-lookup"><span data-stu-id="c98fd-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="c98fd-104">Точки останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-104">Breakpoints</span></span>  
 <span data-ttu-id="c98fd-105">Когда работает отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] , можно переключать точки останова на определенных инструкциях.</span><span class="sxs-lookup"><span data-stu-id="c98fd-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="c98fd-106">Когда выполнение доходит до определенной точки останова, отладчик приостанавливает работу, чтобы вы могли просмотреть такие сведения по отладке, как значения переменных и параметров.</span><span class="sxs-lookup"><span data-stu-id="c98fd-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="c98fd-107">Этими точками останова можно управлять индивидуально в окне редактора или всеми вместе в окне **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c98fd-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="c98fd-108">Точки останова можно изменить — например, указать условия, при которых должно приостанавливаться выполнение, или действия, которые должны выполняться, если выполняется точка останова.</span><span class="sxs-lookup"><span data-stu-id="c98fd-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="c98fd-109">Задачи точки останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="c98fd-110">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="c98fd-110">Task Description</span></span>|<span data-ttu-id="c98fd-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="c98fd-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="c98fd-112">Описано, как задать инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , на которой должен остановиться отладчик.</span><span class="sxs-lookup"><span data-stu-id="c98fd-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="c98fd-113">Переключение точки останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="c98fd-114">Описано, как временно отключить точку останова, а позже снова ее активировать.</span><span class="sxs-lookup"><span data-stu-id="c98fd-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="c98fd-115">Описано удаление точку останова.</span><span class="sxs-lookup"><span data-stu-id="c98fd-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="c98fd-116">Включение, отключение и удаление точек останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="c98fd-117">Описано, как задать условие срабатывания точки останова в зависимости от результата вычисления указанного выражения Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c98fd-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="c98fd-118">Задание условия точки останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="c98fd-119">Описано, как задать счетчик попаданий, чтобы точка останова срабатывала только после того, как инструкция с точкой останова была выполнена указанное число раз.</span><span class="sxs-lookup"><span data-stu-id="c98fd-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="c98fd-120">Настройка счетчика числа попаданий</span><span class="sxs-lookup"><span data-stu-id="c98fd-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="c98fd-121">Описано, как задать фильтр, по которому точка останова будет срабатывать только для указанных процессов или потоков.</span><span class="sxs-lookup"><span data-stu-id="c98fd-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="c98fd-122">Задание фильтра точек останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="c98fd-123">Описано, как задать действие **При попадании** , т. е. пользовательскую операцию, которая выполняется при выполнении инструкции с точкой останова.</span><span class="sxs-lookup"><span data-stu-id="c98fd-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="c98fd-124">Например, печать сообщения.</span><span class="sxs-lookup"><span data-stu-id="c98fd-124">An example would be to print a message.</span></span>|[<span data-ttu-id="c98fd-125">Задание действия в точке останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="c98fd-126">Описано, как изменить местоположение точки останова.</span><span class="sxs-lookup"><span data-stu-id="c98fd-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="c98fd-127">Изменение положения точки останова</span><span class="sxs-lookup"><span data-stu-id="c98fd-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c98fd-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c98fd-128">See Also</span></span>  
 [<span data-ttu-id="c98fd-129">Сведения отладчика Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c98fd-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
