---
title: Редактор циклов for | Документация Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainer.f1
ms.assetid: c4db9df6-d2f4-44da-9f4d-628893e86956
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b610805808e0f392e675ad79f16d2d39886c7f70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655850"
---
# <a name="for-loop-editor"></a><span data-ttu-id="16df6-102">Редактор циклов по элементам</span><span class="sxs-lookup"><span data-stu-id="16df6-102">For Loop Editor</span></span>
  <span data-ttu-id="16df6-103">На странице **Цикл по элементам** диалогового окна **Редактор циклов по элементам** можно настроить цикл, в котором рабочий процесс будет повторяться до тех пор, пока заданное условие не примет значение False.</span><span class="sxs-lookup"><span data-stu-id="16df6-103">Use the **For Loop** page of the **For Loop Editor** dialog box to configure a loop that repeats a workflow until a specified condition evaluates to false.</span></span>  
  
 <span data-ttu-id="16df6-104">Дополнительные сведения о контейнере «цикл по элементам» и его использовании в пакетах см. в разделе [For Loop Container](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="16df6-104">To learn about the For Loop container and how to use it in packages, see [For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="16df6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16df6-105">Options</span></span>  
 <span data-ttu-id="16df6-106">**InitExpression**</span><span class="sxs-lookup"><span data-stu-id="16df6-106">**InitExpression**</span></span>  
 <span data-ttu-id="16df6-107">Необязательный параметр. Выражение для инициализации значений, используемых в цикле.</span><span class="sxs-lookup"><span data-stu-id="16df6-107">Optionally, provide an expression that initializes values used by the loop.</span></span>  
  
 <span data-ttu-id="16df6-108">**EvalExpression**</span><span class="sxs-lookup"><span data-stu-id="16df6-108">**EvalExpression**</span></span>  
 <span data-ttu-id="16df6-109">Выражение, с помощью которого определяется условие завершения или продолжения цикла.</span><span class="sxs-lookup"><span data-stu-id="16df6-109">Provide an expression to evaluate whether the loop should stop or continue.</span></span>  
  
 <span data-ttu-id="16df6-110">**AssignExpression**</span><span class="sxs-lookup"><span data-stu-id="16df6-110">**AssignExpression**</span></span>  
 <span data-ttu-id="16df6-111">Необязательный параметр. Выражение, с помощью которого каждый раз при повторении цикла изменяется условие.</span><span class="sxs-lookup"><span data-stu-id="16df6-111">Optionally, provide an expression that changes a condition each time that the loop repeats.</span></span>  
  
 <span data-ttu-id="16df6-112">**имя**;</span><span class="sxs-lookup"><span data-stu-id="16df6-112">**Name**</span></span>  
 <span data-ttu-id="16df6-113">Содержит уникальное имя для контейнера «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="16df6-113">Provide a unique name for the For Loop container.</span></span> <span data-ttu-id="16df6-114">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="16df6-114">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16df6-115">Имена объектов в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="16df6-115">Object names must be unique within a package.</span></span>  
  
 <span data-ttu-id="16df6-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="16df6-116">**Description**</span></span>  
 <span data-ttu-id="16df6-117">Описание контейнера «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="16df6-117">Provide a description of the For Loop container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16df6-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="16df6-118">See Also</span></span>  
 <span data-ttu-id="16df6-119">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="16df6-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="16df6-120">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="16df6-120">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="16df6-121">[Контейнер «цикл по каждому элементу»](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="16df6-121">[Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="16df6-122">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="16df6-122">Configure a For Loop Container</span></span>](../../2014/integration-services/configure-a-for-loop-container.md)  
  
  
