---
title: Отладка скрипта с помощью точек останова в задаче и компоненте "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657163"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="dc6b2-102">Отладка скрипта с помощью точек останова в задаче и компоненте «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="dc6b2-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="dc6b2-103">Эта процедура описывает способ создания точки останова в скриптах, используемых задачей «Скрипт» и компонентом «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="dc6b2-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="dc6b2-104">После задания точек останова в скрипте в диалоговом окне **Установка точек останова — \<object name>** будет приведен список этих точек останова вместе со встроенными точками останова.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dc6b2-105">В некоторых случаях точки останова из задачи «Скрипт» и компонента скрипта пропускаются.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="dc6b2-106">Дополнительные сведения см. в разделе **Отладка задачи «Скрипт** » статьи [программирование и отладка задачи «Скрипт](../control-flow/script-task.md) » и в разделе « **Отладка компонента скрипта** » раздела [программирование и отладка компонента скрипта] (.. /екстендинг-паккажес-скриптинг/дата-флов-скрипт-компонент/кодинг-анд-дебуггинг-се-скрипт-компонент.мд.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="dc6b2-107">Задание точки останова в скрипте</span><span class="sxs-lookup"><span data-stu-id="dc6b2-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="dc6b2-108">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="dc6b2-109">Дважды щелкните пакет, содержащий скрипт, в котором нужно создать точки останова.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="dc6b2-110">Чтобы открыть задачу "Скрипт", следует перейти на вкладку **Поток управления** и дважды щелкнуть задачу "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="dc6b2-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="dc6b2-111">Чтобы открыть компонент "Скрипт", следует перейти на вкладку **Поток данных** и дважды щелкнуть компонент "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="dc6b2-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="dc6b2-112">Щелкните **Скрипт**, затем нажмите кнопку **Изменить скрипт**.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="dc6b2-113">В среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] набор средств Visual Studio Tools для работы с приложениями (VSTA) найдите строку скрипта, на которой следует установить точку останова, щелкните правой кнопкой мыши, выберите **Точка останова**, а затем **Вставить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="dc6b2-114">Значок точки останова появится на строке с кодом.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="dc6b2-115">В меню **Файл** выберите пункт **Выход**.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="dc6b2-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc6b2-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="dc6b2-117">Чтобы сохранить пакеты, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="dc6b2-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
