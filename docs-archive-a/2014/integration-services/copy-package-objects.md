---
title: Копирование объектов пакета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657213"
---
# <a name="copy-package-objects"></a><span data-ttu-id="00abd-102">Копирование объектов пакета</span><span class="sxs-lookup"><span data-stu-id="00abd-102">Copy Package Objects</span></span>
  <span data-ttu-id="00abd-103">В этом разделе описано, как копировать элементы потока управления, потока данных и диспетчеров соединения внутри пакета или между пакетами.</span><span class="sxs-lookup"><span data-stu-id="00abd-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="00abd-104">Копирование элементов управления и потока данных</span><span class="sxs-lookup"><span data-stu-id="00abd-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="00abd-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий нужные пакеты.</span><span class="sxs-lookup"><span data-stu-id="00abd-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="00abd-106">В обозревателе решений дважды щелкните пакеты, между которыми нужно выполнить копирование.</span><span class="sxs-lookup"><span data-stu-id="00abd-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="00abd-107">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] щелкните вкладку пакета, содержащего элементы для копирования, затем перейдите на вкладку **Поток управления**, **Поток данных**или **Обработчики событий** .</span><span class="sxs-lookup"><span data-stu-id="00abd-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="00abd-108">Выберите поток управления или элементы потока данных для копирования.</span><span class="sxs-lookup"><span data-stu-id="00abd-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="00abd-109">Элементы можно выбирать по одному, нажав клавишу Shift и щелкая нужный элемент, либо выбрать группу элементов, перетаскивая указатель мыши через необходимые элементы.</span><span class="sxs-lookup"><span data-stu-id="00abd-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00abd-110">Управление очередностью и пути, соединяющие элементы, при выборе двух соединяемых ими элементов автоматически не выбираются.</span><span class="sxs-lookup"><span data-stu-id="00abd-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="00abd-111">Чтобы скопировать упорядоченный рабочий процесс (сегмент потока управления или потока данных), убедитесь, что были скопированы ограничение очередностью и пути.</span><span class="sxs-lookup"><span data-stu-id="00abd-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="00abd-112">Щелкните правой кнопкой мыши выбранный элемент и выберите **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="00abd-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="00abd-113">Для копирования элементов в другой пакет щелкните нужный пакет и перейдите на соответствующую вкладку.</span><span class="sxs-lookup"><span data-stu-id="00abd-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00abd-114">Невозможно скопировать поток данных в пакет, пока в нем нет ни одной задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="00abd-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="00abd-115">Щелкните правой кнопкой мыши и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="00abd-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="00abd-116">Копирование диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="00abd-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="00abd-117">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий нужный пакет.</span><span class="sxs-lookup"><span data-stu-id="00abd-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="00abd-118">Дважды щелкните пакет в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="00abd-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="00abd-119">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток управления**, **Поток данных**или **Обработчик события** .</span><span class="sxs-lookup"><span data-stu-id="00abd-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="00abd-120">В поле **Диспетчеры соединений** щелкните правой кнопкой мыши диспетчер подключений и выберите **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="00abd-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="00abd-121">Одновременно можно скопировать только один диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="00abd-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="00abd-122">Для копирования элементов в другой пакет щелкните пакет, в который нужно их скопировать, затем перейдите на вкладку **Поток управления**, **Поток данных**или **Обработчик события** .</span><span class="sxs-lookup"><span data-stu-id="00abd-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="00abd-123">Щелкните правой кнопкой мыши **Диспетчеры соединений** и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="00abd-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00abd-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="00abd-124">See Also</span></span>  
 <span data-ttu-id="00abd-125">[Поток управления](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="00abd-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="00abd-126">[Поток данных](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="00abd-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="00abd-127">[Соединения в службах Integration Services (SSIS)](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="00abd-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="00abd-128">Копирование элементов проекта</span><span class="sxs-lookup"><span data-stu-id="00abd-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
