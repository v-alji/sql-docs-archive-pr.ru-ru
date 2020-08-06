---
title: Подключение задач и контейнеров с помощью управления очередностью по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738612"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="65dd2-102">Соединение задач и контейнеров с помощью элементов управления очередностью по умолчанию</span><span class="sxs-lookup"><span data-stu-id="65dd2-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="65dd2-103">Объекты управления очередностью соединяют два исполняемых объекта.</span><span class="sxs-lookup"><span data-stu-id="65dd2-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="65dd2-104">Исполняемым объектом может быть любая задача, контейнеры «цикл по элементам», «цикл по каждому элементу» или контейнеры последовательности.</span><span class="sxs-lookup"><span data-stu-id="65dd2-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="65dd2-105">Ниже описана процедура настройки поведения по умолчанию для объектов управления очередностью, а также настройка исполняемых объектов с помощью управления очередностью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65dd2-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="65dd2-106">Создание объектов управления очередностью по умолчанию</span><span class="sxs-lookup"><span data-stu-id="65dd2-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="65dd2-107">При первом запуске конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] значение по умолчанию для управления очередностью равно `Success`.</span><span class="sxs-lookup"><span data-stu-id="65dd2-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="65dd2-108">Чтобы изменить в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] значение по умолчанию для управления очередностью, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="65dd2-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="65dd2-109">Настройка значения по умолчанию для управления очередностью</span><span class="sxs-lookup"><span data-stu-id="65dd2-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="65dd2-110">Откройте среду [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65dd2-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="65dd2-111">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="65dd2-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="65dd2-112">В диалоговом окне **Параметры** разверните узел **Конструкторы бизнес-аналитики** , затем разверните **Конструкторы служб Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="65dd2-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="65dd2-113">Щелкните **Автосоединение для потока управления** и выберите **Подключить новую фигуру к выбранной фигуре по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="65dd2-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="65dd2-114">В раскрывающемся списке выберите либо **Использовать ограничение ошибки для новой фигуры** , либо **Использовать ограничение завершения для новой фигуры**.</span><span class="sxs-lookup"><span data-stu-id="65dd2-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="65dd2-115">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65dd2-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="65dd2-116">Создание объекта управления очередностью по умолчанию</span><span class="sxs-lookup"><span data-stu-id="65dd2-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="65dd2-117">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="65dd2-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="65dd2-118">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="65dd2-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="65dd2-119">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="65dd2-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="65dd2-120">В области конструктора на вкладке **Поток управления** щелкните задачу или контейнер и перетащите их соединители на исполняемый объект, к которому нужно применить управление очередностью.</span><span class="sxs-lookup"><span data-stu-id="65dd2-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="65dd2-121">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="65dd2-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65dd2-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="65dd2-122">See Also</span></span>  
 <span data-ttu-id="65dd2-123">[Управление очередностью](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="65dd2-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="65dd2-124">[Установка значения управления очередностью с помощью контекстного меню](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="65dd2-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="65dd2-125">[Задание свойств управления очередностью](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="65dd2-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="65dd2-126">Использование выражения в элементах управлении очередностью</span><span class="sxs-lookup"><span data-stu-id="65dd2-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
