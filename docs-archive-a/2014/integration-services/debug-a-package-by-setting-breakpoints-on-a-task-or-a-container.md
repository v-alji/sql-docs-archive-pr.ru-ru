---
title: Отладка пакета путем установки точек останова в задаче или контейнере | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656479"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="8202d-102">Выполнение отладки пакета путем установки точек останова для задачи или контейнера</span><span class="sxs-lookup"><span data-stu-id="8202d-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="8202d-103">Эта процедура описывает, как установить точки останова в пакете, задаче, контейнерах «цикл по элементам», «цикл по каждому элементу» и контейнере последовательности.</span><span class="sxs-lookup"><span data-stu-id="8202d-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="8202d-104">Установка точки останова в пакете, задаче или контейнере</span><span class="sxs-lookup"><span data-stu-id="8202d-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="8202d-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="8202d-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8202d-106">Дважды щелкните пакет, для которого следует установить точки останова.</span><span class="sxs-lookup"><span data-stu-id="8202d-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="8202d-107">В конструкторе служб SSIS сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="8202d-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="8202d-108">Чтобы установить точки останова в объекте пакета, перейдите на вкладку **Поток управления** , поместите курсор где-либо на заднем плане области конструктора, щелкните правой кнопкой мыши и выберите пункт **Изменить точки останова**.</span><span class="sxs-lookup"><span data-stu-id="8202d-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="8202d-109">Чтобы установить точки останова в потоке управления пакета, перейдите на вкладку **Поток управления** , правой кнопкой мыши щелкните задачу, контейнер "цикл по элементам", "цикл по каждому элементу" или контейнер последовательности и выберите пункт **Изменить точки останова**.</span><span class="sxs-lookup"><span data-stu-id="8202d-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="8202d-110">Чтобы установить точки останова в обработчике события, перейдите на вкладку **Обработчик события** , щелкните правой кнопкой мыши задачу, контейнер "цикл по элементам", "цикл по каждому элементу" или контейнер последовательности и выберите пункт **Изменить точки останова**.</span><span class="sxs-lookup"><span data-stu-id="8202d-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="8202d-111">В диалоговом окне **Задание точек останова\<container name>** выберите точки останова для включения.</span><span class="sxs-lookup"><span data-stu-id="8202d-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="8202d-112">При необходимости измените тип счетчика попаданий и значение числа попаданий для каждой точки останова.</span><span class="sxs-lookup"><span data-stu-id="8202d-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="8202d-113">Чтобы сохранить пакеты, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="8202d-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8202d-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8202d-114">See Also</span></span>  
 <span data-ttu-id="8202d-115">[Инструменты устранения неполадок при разработке пакета](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="8202d-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="8202d-116">[Отладка скрипта путем установки точек останова в задаче «Скрипт» и компоненте «Скрипт»](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="8202d-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="8202d-117">[Написание кода и отладка задачи «Скрипт»](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="8202d-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="8202d-118">Кодирование и отладка компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="8202d-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
