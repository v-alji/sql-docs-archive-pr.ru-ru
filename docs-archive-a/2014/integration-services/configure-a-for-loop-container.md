---
title: Настройка контейнера «цикл по каждому элементу» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655883"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="24a95-102">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="24a95-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="24a95-103">В процедуре описывается, как настроить контейнер «цикл по элементам» с помощью диалогового окна **Редактор циклов по элементам** .</span><span class="sxs-lookup"><span data-stu-id="24a95-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="24a95-104">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="24a95-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="24a95-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]дважды щелкните контейнер "цикл по элементам", чтобы открыть **Редактор циклов по элементам**.</span><span class="sxs-lookup"><span data-stu-id="24a95-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="24a95-106">При необходимости измените имя и описание контейнера «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="24a95-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="24a95-107">При необходимости введите выражение инициализации в текстовое поле **InitExpression** .</span><span class="sxs-lookup"><span data-stu-id="24a95-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="24a95-108">Введите выражение в текстовое поле **EvalExpression** .</span><span class="sxs-lookup"><span data-stu-id="24a95-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24a95-109">Выражение должно иметь логическое значение.</span><span class="sxs-lookup"><span data-stu-id="24a95-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="24a95-110">Если значением этого выражения будет `false`, выполнение цикла останавливается.</span><span class="sxs-lookup"><span data-stu-id="24a95-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="24a95-111">При необходимости введите выражение присвоения в текстовое поле **AssignExpression** .</span><span class="sxs-lookup"><span data-stu-id="24a95-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="24a95-112">При необходимости щелкните **Выражения** и на странице **Выражения** создайте выражения свойств для свойств контейнера «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="24a95-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="24a95-113">Дополнительные сведения см. в разделе [Добавление или изменение выражение свойства](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="24a95-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="24a95-114">Щелкните **ОК** , чтобы закрыть **Редактор циклов For**.</span><span class="sxs-lookup"><span data-stu-id="24a95-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a95-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="24a95-115">See Also</span></span>  
 <span data-ttu-id="24a95-116">[Контейнер «цикл по каждому»](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="24a95-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="24a95-117">[Выражения&#41; Integration Services &#40;SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="24a95-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="24a95-118">Использование выражений свойств в пакетах</span><span class="sxs-lookup"><span data-stu-id="24a95-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
