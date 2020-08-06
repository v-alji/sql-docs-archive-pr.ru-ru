---
title: Переключение точки останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667016"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="8be08-102">Переключение точки останова</span><span class="sxs-lookup"><span data-stu-id="8be08-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="8be08-103">Установка точки останова для инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] называется переключением точки останова.</span><span class="sxs-lookup"><span data-stu-id="8be08-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="8be08-104">Точки останова</span><span class="sxs-lookup"><span data-stu-id="8be08-104">Breakpoints</span></span>  
 <span data-ttu-id="8be08-105">Установленная точка останова отображается значком на серой полосе слева от инструкции.</span><span class="sxs-lookup"><span data-stu-id="8be08-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="8be08-106">Этот значок называется глифом точки останова.</span><span class="sxs-lookup"><span data-stu-id="8be08-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="8be08-107">применяются к полной инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8be08-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="8be08-108">Когда точка останова включена, отладчик подсвечивает связанную инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8be08-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="8be08-109">При наличии в строке нескольких инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] можно включить точку останова для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="8be08-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="8be08-110">При щелчке серой полосы в левой части окна переключается точка останова для первой инструкции в строке.</span><span class="sxs-lookup"><span data-stu-id="8be08-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="8be08-111">Чтобы переключить точку останова следующей инструкции, выделите любую часть этой инструкции или переместите курсор в нее и нажмите клавишу F9 либо выберите команду **Переключить точку останова** в меню **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="8be08-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="8be08-112">Нескольким точкам останова в одной строке соответствует одна глифом точки останова.</span><span class="sxs-lookup"><span data-stu-id="8be08-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="8be08-113">После переключения точки останова можно выполнять различные действия с точкой останова, например изменить свойства или временно отключить.</span><span class="sxs-lookup"><span data-stu-id="8be08-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="8be08-114">Дополнительные сведения см. в разделе [Точки останова Transact-SQL](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="8be08-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="8be08-115">Переключение точки останова</span><span class="sxs-lookup"><span data-stu-id="8be08-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="8be08-116">**Переключение точки останова на инструкции языка Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="8be08-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="8be08-117">Щелкните серую полосу слева от инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8be08-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="8be08-118">Выделите любую часть инструкции или переместите курсор в инструкцию и выполните любое из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8be08-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="8be08-119">Нажмите клавишу F9.</span><span class="sxs-lookup"><span data-stu-id="8be08-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="8be08-120">В меню **Отладка** выбрать пункт **Переключить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="8be08-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
