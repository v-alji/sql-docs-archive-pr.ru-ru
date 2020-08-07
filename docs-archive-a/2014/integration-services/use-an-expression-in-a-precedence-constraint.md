---
title: Использование выражения в ограничении очередностью | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732733"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="abee1-102">Использование выражения в элементах управлении очередностью</span><span class="sxs-lookup"><span data-stu-id="abee1-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="abee1-103">Эта процедура описывает добавление выражений к объекту управления очередностью с помощью диалогового окна **Редактор управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="abee1-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="abee1-104">Перед добавлением выражения к управлению очередностью пакет должен содержать по меньшей мере два исполняемых объекта (задачи или контейнера), которые должны быть соединены объектом управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="abee1-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="abee1-105">Добавление выражения к элементу управления очередностью</span><span class="sxs-lookup"><span data-stu-id="abee1-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="abee1-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="abee1-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="abee1-107">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="abee1-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="abee1-108">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="abee1-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="abee1-109">В области конструктора на вкладке **Поток управления** дважды щелкните объект управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="abee1-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="abee1-110">Открывается **Редактор управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="abee1-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="abee1-111">Выберите пункт **Выражение**, **Выражение и ограничение**или **Выражение или ограничение** в списке **Вычислительная операция** .</span><span class="sxs-lookup"><span data-stu-id="abee1-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="abee1-112">Введите выражение в текстовое поле **Выражение** или запустите построитель выражений, чтобы создать выражение.</span><span class="sxs-lookup"><span data-stu-id="abee1-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="abee1-113">Чтобы проверить правильность синтаксиса выражения, нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="abee1-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="abee1-114">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="abee1-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abee1-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="abee1-115">See Also</span></span>  
 <span data-ttu-id="abee1-116">[Управление очередностью](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="abee1-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="abee1-117">[Подключение задач и контейнеров с помощью управления очередностью по умолчанию](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="abee1-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="abee1-118">[Установка значения управления очередностью с помощью контекстного меню](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="abee1-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="abee1-119">[Задание свойств управления очередностью](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="abee1-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="abee1-120">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="abee1-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
