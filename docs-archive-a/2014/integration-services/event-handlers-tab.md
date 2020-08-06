---
title: Вкладка "обработчики событий" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665028"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="e47b5-102">Вкладка «Обработчики событий»</span><span class="sxs-lookup"><span data-stu-id="e47b5-102">Event Handlers Tab</span></span>
  <span data-ttu-id="e47b5-103">Используйте вкладку **Обработчики событий** конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , чтобы сформировать поток управления в пакете служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e47b5-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="e47b5-104">Обработчик события запускается в ответ на событие, инициированное либо пакетом, либо задачей или контейнером в пакете.</span><span class="sxs-lookup"><span data-stu-id="e47b5-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e47b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e47b5-105">Options</span></span>  
 <span data-ttu-id="e47b5-106">**Исполняемый объект**</span><span class="sxs-lookup"><span data-stu-id="e47b5-106">**Executable**</span></span>  
 <span data-ttu-id="e47b5-107">Выберите исполняемый объект, для которого необходимо создать обработчик события.</span><span class="sxs-lookup"><span data-stu-id="e47b5-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="e47b5-108">Исполняемый объект может быть либо пакетом, либо задачей или контейнером в пакете.</span><span class="sxs-lookup"><span data-stu-id="e47b5-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="e47b5-109">**Обработчик событий**</span><span class="sxs-lookup"><span data-stu-id="e47b5-109">**Event handler**</span></span>  
 <span data-ttu-id="e47b5-110">Выберите тип обработчика события.</span><span class="sxs-lookup"><span data-stu-id="e47b5-110">Select a type of event handler.</span></span> <span data-ttu-id="e47b5-111">Создайте обработчик события, перетащив элементы из **Области элементов**.</span><span class="sxs-lookup"><span data-stu-id="e47b5-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="e47b5-112">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="e47b5-112">**Delete**</span></span>  
 <span data-ttu-id="e47b5-113">Выберите обработчик события и удалите его из пакета, нажав кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e47b5-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="e47b5-114">**Щелкните здесь, чтобы создать \<event handler name> для исполняемого файла \<executable name>**</span><span class="sxs-lookup"><span data-stu-id="e47b5-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="e47b5-115">Нажмите, чтобы создать обработчик события.</span><span class="sxs-lookup"><span data-stu-id="e47b5-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="e47b5-116">Создайте поток управления, перетащив графические объекты, которые представляют задачи и контейнеры служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , из **Области элементов** в область конструктора вкладки **Обработчики событий** , соединяя затем объекты при помощи объектов управления очередностью, чтобы определить последовательность их запуска.</span><span class="sxs-lookup"><span data-stu-id="e47b5-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="e47b5-117">Кроме того, чтобы добавить заметки, щелкните правой кнопкой мыши в области конструктора и выберите из меню команду **Добавить заметку**.</span><span class="sxs-lookup"><span data-stu-id="e47b5-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47b5-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="e47b5-118">See Also</span></span>  
 <span data-ttu-id="e47b5-119">[Обработчики событий в службах Integration Services (SSIS)](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="e47b5-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="e47b5-120">[Поток управления](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e47b5-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="e47b5-121">[Конструктор служб SSIS](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e47b5-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="e47b5-122">Обработчики событий в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="e47b5-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
