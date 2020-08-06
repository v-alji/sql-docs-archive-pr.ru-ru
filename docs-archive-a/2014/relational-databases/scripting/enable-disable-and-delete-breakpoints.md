---
title: Включение, отключение и удаление точек останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668243"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="c17c0-102">Включение, отключение и удаление точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="c17c0-103">Для просмотра всех открытых точек останова и управления ими используется окно **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="c17c0-104">Используйте данное окно для просмотра сведений о точках останова, а также для выполнения таких действий, как удаление, отключение или включение точек останова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="c17c0-105">Окно точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="c17c0-106">В окне **Точки останова** приводятся такие сведения, как строка кода, в которой расположена точка останова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="c17c0-107">Кроме того, в окне **Точки останова** можно удалять, отключать и включать точки останова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="c17c0-108">Дополнительные сведения об окне **Точки останова** см. в разделе [Точки останова Window](transact-sql-debugger-breakpoints-window.md).</span><span class="sxs-lookup"><span data-stu-id="c17c0-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="c17c0-109">Отключение точки останова предотвращает приостановку выполнения с ее помощью, однако определение точки при этом остается на месте на тот случай, если в будущем потребуется включить ее снова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="c17c0-110">Удаление точки останова не может быть отменено впоследствии.</span><span class="sxs-lookup"><span data-stu-id="c17c0-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="c17c0-111">Необходимо перевести новую точку останова во включенное состояние для приостановки выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="c17c0-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="c17c0-112">Открытие окна точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="c17c0-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="c17c0-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="c17c0-114">Открыть окно **Точки останова** можно одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="c17c0-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-115">В меню **Отладка** выберите пункт **Окна**, а затем **Точки останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="c17c0-116">На панели инструментов **Отладка** нажмите кнопку **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="c17c0-117">Нажмите сочетание клавиш CTRL+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="c17c0-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="c17c0-118">Отключение отдельной точки останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="c17c0-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="c17c0-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="c17c0-120">Отключить отдельную точку останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-121">В окне редактора запросов щелкните точку останова правой кнопкой мыши и выберите команду **Отключить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="c17c0-122">В окне «Точки останова» снимите флажок слева от точки останова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="c17c0-123">Отключение всех точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="c17c0-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="c17c0-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="c17c0-125">Отключить все точки останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-126">В меню **Отладка** выберите пункт **Отключить все точки останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="c17c0-127">На панели инструментов окна **Точки останова** нажмите кнопку **Отключить все точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="c17c0-128">Включение отдельной точки останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="c17c0-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="c17c0-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="c17c0-130">Включить отдельную точку останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-131">В окне редактора запросов щелкните точку останова правой кнопкой мыши и выберите команду **Включить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="c17c0-132">В окне точек останова установите флажок слева от точки останова.</span><span class="sxs-lookup"><span data-stu-id="c17c0-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="c17c0-133">Включение всех точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="c17c0-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="c17c0-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="c17c0-135">Включить все точки останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-136">В меню **Отладка** выбрать пункт **Включить все точки останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="c17c0-137">На панели инструментов окна **Точки останова** нажмите кнопку **Включить все точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="c17c0-138">Удаление отдельной точки останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="c17c0-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="c17c0-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="c17c0-140">Удалить отдельную точку останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-141">В окне редактора запросов щелкните точку останова правой кнопкой мыши и выберите команду **Удалить точку останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="c17c0-142">В окне "Точки останова" щелкните точку останова правой кнопкой мыши и в контекстном меню выберите команду **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="c17c0-143">В окне «Точки останова» выделите точку останова и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="c17c0-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="c17c0-144">Удаление всех точек останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="c17c0-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="c17c0-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="c17c0-146">Удалить все точки останова можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="c17c0-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="c17c0-147">В меню **Отладка** выбрать пункт **Удалить все точки останова**.</span><span class="sxs-lookup"><span data-stu-id="c17c0-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="c17c0-148">На панели инструментов окна **Точки останова** нажмите кнопку **Удалить все точки останова** .</span><span class="sxs-lookup"><span data-stu-id="c17c0-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17c0-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="c17c0-149">See Also</span></span>  
 [<span data-ttu-id="c17c0-150">Переключение точки останова</span><span class="sxs-lookup"><span data-stu-id="c17c0-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
