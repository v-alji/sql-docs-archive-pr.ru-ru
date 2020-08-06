---
title: Просмотр объектов пакета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666117"
---
# <a name="view-package-objects"></a><span data-ttu-id="ab166-102">просмотр объектов пакета</span><span class="sxs-lookup"><span data-stu-id="ab166-102">View Package Objects</span></span>
  <span data-ttu-id="ab166-103">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] вкладка **Обозреватель пакетов** предоставляет режим обозревателя.</span><span class="sxs-lookup"><span data-stu-id="ab166-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="ab166-104">В данном режиме отображается иерархия контейнеров архитектуры [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab166-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="ab166-105">Контейнер пакетов стоит на самом верху иерархии. При разворачивании пакета можно просмотреть все соединения, исполняемые объекты, обработчики событий, регистраторы, объекты управления очередностью и переменные.</span><span class="sxs-lookup"><span data-stu-id="ab166-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="ab166-106">Исполняемые объекты, то есть контейнеры и задачи в пакете, могут содержать обработчики событий, элементы управления очередностью и переменные.</span><span class="sxs-lookup"><span data-stu-id="ab166-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ab166-107">поддерживают вложенную иерархию контейнеров, а контейнеры «цикл по элементам», «цикл по каждому элементу» и контейнер последовательности могут содержать другие исполняемые объекты.</span><span class="sxs-lookup"><span data-stu-id="ab166-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="ab166-108">Если пакет содержит поток данных, то вкладка **Обозреватель пакетов** содержит задачу потока данных, а также папку **Компоненты** , которая содержит список компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="ab166-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="ab166-109">На вкладке **Обозреватель пакетов** можно удалять объекты из пакета, а также открыть окно **Свойства** для просмотра свойств объектов.</span><span class="sxs-lookup"><span data-stu-id="ab166-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="ab166-110">На следующей диаграмме показана древовидная структура простого пакета.</span><span class="sxs-lookup"><span data-stu-id="ab166-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="ab166-111">![Снимок экрана: вкладка "Обозреватель пакетов"](media/packageexplorer.gif "Снимок экрана: вкладка "Обозреватель пакетов"")</span><span class="sxs-lookup"><span data-stu-id="ab166-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="ab166-112">Просмотр содержимого пакета</span><span class="sxs-lookup"><span data-stu-id="ab166-112">To view package content</span></span>

-   [<span data-ttu-id="ab166-113">Просмотр объектов пакета в обозревателе пакетов</span><span class="sxs-lookup"><span data-stu-id="ab166-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="ab166-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab166-114">See Also</span></span>
 <span data-ttu-id="ab166-115">[Integration Services задачи](control-flow/integration-services-tasks.md) [Integration Services](control-flow/integration-services-containers.md) управление [очередностью](control-flow/precedence-constraints.md) контейнеров [Integration Services &#40;SSIS&#41; переменные](integration-services-ssis-variables.md) [Integration Services &#40;службы](integration-services-ssis-event-handlers.md) SSIS&#41; [Журнал](performance/integration-services-ssis-logging.md) Integration Services</span><span class="sxs-lookup"><span data-stu-id="ab166-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>


