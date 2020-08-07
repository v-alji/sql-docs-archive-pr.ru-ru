---
title: Задание условия точки останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733841"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="ee24f-102">Задание условия точки останова</span><span class="sxs-lookup"><span data-stu-id="ee24f-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="ee24f-103">Условием для точки останова служит выражение [!INCLUDE[tsql](../../includes/tsql-md.md)] , проверяемое отладчиком по достижению точки останова.</span><span class="sxs-lookup"><span data-stu-id="ee24f-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="ee24f-104">Если достигнуто указанное число попаданий или удовлетворяется указанное условие, то отладчик останавливает выполнение или выполняет действие, заданное для точки останова.</span><span class="sxs-lookup"><span data-stu-id="ee24f-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="ee24f-105">Задание условий</span><span class="sxs-lookup"><span data-stu-id="ee24f-105">Specifying Conditions</span></span>  
 <span data-ttu-id="ee24f-106">Необходимо задать допустимое выражение Transact-SQL, результатом вычисления которого является логическое значение.</span><span class="sxs-lookup"><span data-stu-id="ee24f-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="ee24f-107">Дополнительные сведения см. в разделе [Выражения (Transact-SQL)](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee24f-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="ee24f-108">Если задать условие точки останова с недопустимым синтаксисом, немедленно появится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ee24f-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="ee24f-109">Если задать условие с допустимым синтаксисом, но недопустимой семантикой, предупреждение появится, когда точка останова будет достигнута в первый раз.</span><span class="sxs-lookup"><span data-stu-id="ee24f-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="ee24f-110">В любом случае отладчик прервет выполнение, как только будет достигнута недопустимая точка останова.</span><span class="sxs-lookup"><span data-stu-id="ee24f-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="ee24f-111">Задание условия</span><span class="sxs-lookup"><span data-stu-id="ee24f-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="ee24f-112">В окне редактора щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Условие** .</span><span class="sxs-lookup"><span data-stu-id="ee24f-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="ee24f-113">-или-</span><span class="sxs-lookup"><span data-stu-id="ee24f-113">-or-</span></span>  
  
     <span data-ttu-id="ee24f-114">В окне **Точки останова** щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Условие** .</span><span class="sxs-lookup"><span data-stu-id="ee24f-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ee24f-115">Введите в поле **Условие** диалогового окна **Условие точки останова** допустимое логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="ee24f-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="ee24f-116">Выберите **значение true** , если требуется прервать выполнение при вычислении выражения `true` , или если выбрать параметр **изменено** , если требуется прервать выполнение при изменении значения выражения.</span><span class="sxs-lookup"><span data-stu-id="ee24f-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee24f-117">Отладчик не проверяет это логическое выражение, пока не будет достигнута первая точка останова.</span><span class="sxs-lookup"><span data-stu-id="ee24f-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="ee24f-118">Если выбрать **Изменилось**, отладчик не будет считать первую проверку изменением и, следовательно, не будет прерывать при ней исполнение.</span><span class="sxs-lookup"><span data-stu-id="ee24f-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee24f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee24f-119">See Also</span></span>  
 <span data-ttu-id="ee24f-120">[Укажите число попаданий](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="ee24f-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="ee24f-121">Задание действия в точке останова</span><span class="sxs-lookup"><span data-stu-id="ee24f-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
