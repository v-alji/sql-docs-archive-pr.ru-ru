---
title: Редактор управления очередностью | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657139"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="73801-102">Редактор управления очередностью</span><span class="sxs-lookup"><span data-stu-id="73801-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="73801-103">Диалоговое окно **Редактор ограничений очередностью** используется для настройки ограничений очередностью.</span><span class="sxs-lookup"><span data-stu-id="73801-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73801-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="73801-104">Options</span></span>  
 <span data-ttu-id="73801-105">**Вычислительная операция**</span><span class="sxs-lookup"><span data-stu-id="73801-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="73801-106">Определяет вычислительную операцию, которую использует ограничение очередностью.</span><span class="sxs-lookup"><span data-stu-id="73801-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="73801-107">Операциями могут быть: **Ограничение**, **Выражение**, **Выражение и ограничение** и **Выражение или ограничение**.</span><span class="sxs-lookup"><span data-stu-id="73801-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="73801-108">**Значение**</span><span class="sxs-lookup"><span data-stu-id="73801-108">**Value**</span></span>  
 <span data-ttu-id="73801-109">Укажите ограничение по значению: **Успешно**, **Сбой** или **Завершение**.</span><span class="sxs-lookup"><span data-stu-id="73801-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73801-110"> Строка элементов управления очередностью имеет зеленый цвет для значения **Успех**, синий — для значения **Завершение**и выделяется для значения **Неудача**.</span><span class="sxs-lookup"><span data-stu-id="73801-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="73801-111">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="73801-111">**Expression**</span></span>  
 <span data-ttu-id="73801-112">При использовании действий **Выражение**, **Выражение и ограничение**или **Выражение или ограничение**введите выражение или запустите построитель выражений для создания выражения.</span><span class="sxs-lookup"><span data-stu-id="73801-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="73801-113">Выражение должно иметь логическое значение.</span><span class="sxs-lookup"><span data-stu-id="73801-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="73801-114">**Тест**</span><span class="sxs-lookup"><span data-stu-id="73801-114">**Test**</span></span>  
 <span data-ttu-id="73801-115">Проверка выражения.</span><span class="sxs-lookup"><span data-stu-id="73801-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="73801-116">**Логическое И**</span><span class="sxs-lookup"><span data-stu-id="73801-116">**Logical AND**</span></span>  
 <span data-ttu-id="73801-117">Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе.</span><span class="sxs-lookup"><span data-stu-id="73801-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="73801-118">Все ограничения должны иметь значение `True`.</span><span class="sxs-lookup"><span data-stu-id="73801-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73801-119">Этот тип элементов управления очередностью имеет вид сплошной зеленой или синей линии либо выделяется.</span><span class="sxs-lookup"><span data-stu-id="73801-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="73801-120">**Логическое ИЛИ**</span><span class="sxs-lookup"><span data-stu-id="73801-120">**Logical OR**</span></span>  
 <span data-ttu-id="73801-121">Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе.</span><span class="sxs-lookup"><span data-stu-id="73801-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="73801-122">По крайней мере, одно ограничение должно иметь значение `True`.</span><span class="sxs-lookup"><span data-stu-id="73801-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73801-123">Этот тип элементов управления очередностью имеет вид пунктирной зеленой или синей линии либо выделяется.</span><span class="sxs-lookup"><span data-stu-id="73801-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73801-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="73801-124">See Also</span></span>  
 <span data-ttu-id="73801-125">[Управление очередностью](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="73801-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="73801-126">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="73801-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="73801-127">[Контейнеры Integration Services](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="73801-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="73801-128">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="73801-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
