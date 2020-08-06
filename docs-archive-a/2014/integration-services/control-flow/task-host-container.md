---
title: Контейнер "Сервер задач" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667341"
---
# <a name="task-host-container"></a><span data-ttu-id="e4db5-102">контейнер «Сервер задач»</span><span class="sxs-lookup"><span data-stu-id="e4db5-102">Task Host Container</span></span>
  <span data-ttu-id="e4db5-103">Контейнер «Сервер задач» содержит одну задачу.</span><span class="sxs-lookup"><span data-stu-id="e4db5-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="e4db5-104">В конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] сервер задач не настраивается отдельно; он настраивается при определении свойств содержащейся в нем задачи.</span><span class="sxs-lookup"><span data-stu-id="e4db5-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="e4db5-105">Дополнительные сведения о задачах, которые содержат контейнеры узла задач см. в разделе [Integration Services Tasks](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="e4db5-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="e4db5-106">Этот контейнер расширяет применение переменных и обработчиков событий до уровня задач.</span><span class="sxs-lookup"><span data-stu-id="e4db5-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="e4db5-107">Дополнительные сведения см. в разделах [Обработчики событий в службах Integration Services (SSIS)](../integration-services-ssis-event-handlers.md) и [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e4db5-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="e4db5-108">Настройка сервера задач</span><span class="sxs-lookup"><span data-stu-id="e4db5-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="e4db5-109">Задать свойства можно в окне **Свойства** среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="e4db5-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="e4db5-110">Дополнительные сведения о настройке свойств этих свойств в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="e4db5-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="e4db5-111">Дополнительные сведения о настройке этих свойств программными средствами см. в разделе <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="e4db5-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e4db5-112">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e4db5-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e4db5-113">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="e4db5-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e4db5-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4db5-114">See Also</span></span>  
 [<span data-ttu-id="e4db5-115">Контейнеры служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e4db5-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
