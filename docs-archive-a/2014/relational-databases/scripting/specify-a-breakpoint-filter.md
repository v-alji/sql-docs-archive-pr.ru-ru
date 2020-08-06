---
title: Задание фильтра точек останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664839"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="5dc9b-102">Задание фильтра точек останова</span><span class="sxs-lookup"><span data-stu-id="5dc9b-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="5dc9b-103">Фильтр для точек останова ограничивает действие точки останова определенными компьютерами, процессами операционной системы и потоками.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="5dc9b-104">Фильтры точек останова обычно используются при отладке параллельных приложений.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="5dc9b-105">Вопросы применения фильтров</span><span class="sxs-lookup"><span data-stu-id="5dc9b-105">Filter Considerations</span></span>  
 <span data-ttu-id="5dc9b-106">Обычно фильтры точек останова используют вместе с отладчиком [!INCLUDE[tsql](../../includes/tsql-md.md)] , потому что скрипты и хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] не являются параллельными приложениями.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="5dc9b-107">Задание фильтра точки останова</span><span class="sxs-lookup"><span data-stu-id="5dc9b-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="5dc9b-108">В окне редактора щелкните метку точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="5dc9b-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="5dc9b-109">-или-</span><span class="sxs-lookup"><span data-stu-id="5dc9b-109">-or-</span></span>  
  
     <span data-ttu-id="5dc9b-110">В окне **Точки останова** щелкните метку точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="5dc9b-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5dc9b-111">В диалоговом окне **Фильтры точки останова** используйте флажок **Фильтр** для указания компьютеров по имени или процессов и потоков операционной системы по имени или идентификационному номеру.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="5dc9b-112">`MachineName` — это компьютер, на котором запущен экземпляр Database Engine.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="5dc9b-113">`ProcessID` и `ProcessName` — это процесс операционной системы, в котором исполняется экземпляр компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="5dc9b-114">`ThreadID` и `ThreadName` — это поток операционной системы, в котором выполняется пакет, процедура или функция [!INCLUDE[tsql](../../includes/tsql-md.md)] на экземпляре Database Engine.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="5dc9b-115">Нажмите кнопку **ОК** , чтобы внести изменения, либо кнопку **Отмена** , чтобы выйти без их применения.</span><span class="sxs-lookup"><span data-stu-id="5dc9b-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc9b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5dc9b-116">See Also</span></span>  
 <span data-ttu-id="5dc9b-117">[Задание условия точки останова](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="5dc9b-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="5dc9b-118">[Настройка счетчика числа попаданий](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="5dc9b-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="5dc9b-119">Задание действия в точке останова</span><span class="sxs-lookup"><span data-stu-id="5dc9b-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
