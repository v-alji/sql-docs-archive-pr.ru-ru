---
title: Скрипт отладки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736506"
---
# <a name="debugging-script"></a><span data-ttu-id="86426-102">Скрипт отладки</span><span class="sxs-lookup"><span data-stu-id="86426-102">Debugging Script</span></span>
  <span data-ttu-id="86426-103">Скрипты, использующие задачу и компонент "Скрипт", создаются в средствах для приложений [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (VSTA).</span><span class="sxs-lookup"><span data-stu-id="86426-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="86426-104">Можно задавать и использовать в скриптах точки останова в VSTA.</span><span class="sxs-lookup"><span data-stu-id="86426-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="86426-105">VSTA дает возможность управлять точками останова, но для этого вы можете также пользоваться и диалоговым окном **Задание точек останова** конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86426-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="86426-106">Дополнительные сведения см. в статье [Отладка потока управления](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="86426-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="86426-107">Диалоговое окно **Задание точек останова** включает точки останова скрипта.</span><span class="sxs-lookup"><span data-stu-id="86426-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="86426-108">Они содержатся внизу списка точек останова и отображают номер строки и имя функции, в которой появляется точка останова.</span><span class="sxs-lookup"><span data-stu-id="86426-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="86426-109">Точки останова скрипта вы можете удалять с помощью диалогового окна **Задание точек останова** .</span><span class="sxs-lookup"><span data-stu-id="86426-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="86426-110">Во время выполнения точки останова, заданные для строк кода скрипта, объединяются с точками останова, заданными для пакета или задач и контейнеров в пакете.</span><span class="sxs-lookup"><span data-stu-id="86426-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="86426-111">Отладчик может выполняться от точки останова в скрипте до точки останова, заданной для пакета задачи или контейнера, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="86426-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="86426-112">Например, для пакета могут существовать точки останова, заданные условиями останова, возникающими при получении пакетом событий **OnPreExecute** и **OnPostExecute** , а также задача «Скрипт» с точками останова для строк скрипта.</span><span class="sxs-lookup"><span data-stu-id="86426-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="86426-113">В этом случае пакет может приостановить выполнение по условию останова, связанного с событием **OnPreExecute** , выполниться до точки останова в скрипте и в заключение до условия останова, связанного с событием **OnPostExecute** .</span><span class="sxs-lookup"><span data-stu-id="86426-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="86426-114">Дополнительные сведения об отладке задачи и компонента «Скрипт» см. в разделах [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) и [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="86426-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="86426-115">Задание точки останова в Visual Studio для приложений</span><span class="sxs-lookup"><span data-stu-id="86426-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="86426-116">Отладка скрипта с помощью точек останова в задаче и компоненте «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="86426-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="86426-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="86426-117">See Also</span></span>  
 [<span data-ttu-id="86426-118">Инструменты устранения неполадок при разработке пакета</span><span class="sxs-lookup"><span data-stu-id="86426-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
