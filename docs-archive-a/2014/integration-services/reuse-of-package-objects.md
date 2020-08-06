---
title: Повторное использование объектов пакета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729586"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="c87cd-102">Повторное использование объектов пакета</span><span class="sxs-lookup"><span data-stu-id="c87cd-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="c87cd-103">Функциональные возможности пакетов, которые требуется использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="c87cd-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="c87cd-104">Например, создан набор задач, и необходимо повторно совместно использовать элементы как группу, или необходимо повторно использовать отдельный элемент, такой как диспетчер соединений, созданный в другом проекте служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c87cd-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="c87cd-105">Копирование и вставка</span><span class="sxs-lookup"><span data-stu-id="c87cd-105">Copy and Paste</span></span>  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="c87cd-106">и Конструктор [!INCLUDE[ssIS](../includes/ssis-md.md)] поддерживают копирование и вставку пакетных объектов, которые могут включать элементы потоков управления и данных, а также диспетчеры соединений.</span><span class="sxs-lookup"><span data-stu-id="c87cd-106">and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="c87cd-107">Можно выполнять копирование и вставку между проектами и пакетами.</span><span class="sxs-lookup"><span data-stu-id="c87cd-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="c87cd-108">Если в решении содержится несколько проектов, можно выполнять копирование между проектами, и проекты могут принадлежать разным типам.</span><span class="sxs-lookup"><span data-stu-id="c87cd-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="c87cd-109">Если решение содержит несколько пакетов, можно выполнять копирование и вставку между ними.</span><span class="sxs-lookup"><span data-stu-id="c87cd-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="c87cd-110">Пакеты могут находиться в одном или разных проектах служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c87cd-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="c87cd-111">Однако объекты пакета могут иметь зависимости от других объектов, без которых они недействительны.</span><span class="sxs-lookup"><span data-stu-id="c87cd-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="c87cd-112">Например, задача «Выполнение SQL» использует диспетчер соединений, который также необходимо скопировать, чтобы задача работала.</span><span class="sxs-lookup"><span data-stu-id="c87cd-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="c87cd-113">Также некоторые объекты пакета требуют, чтобы пакет уже содержал определенный объект, а при отсутствии этого объекта успешная вставка скопированных объектов в пакет невозможна.</span><span class="sxs-lookup"><span data-stu-id="c87cd-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="c87cd-114">Например, невозможно вставить поток данных в пакет, если он не содержит хотя бы одну задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="c87cd-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="c87cd-115">Может оказаться, что одни и те же пакеты копируются повторно.</span><span class="sxs-lookup"><span data-stu-id="c87cd-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="c87cd-116">Чтобы избежать процесса копирования, можно обозначить эти пакеты как шаблоны и использовать их при создании пакетов.</span><span class="sxs-lookup"><span data-stu-id="c87cd-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="c87cd-117">При копировании объекта пакета службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] автоматически присваивают новый идентификатор GUID свойству `ID` нового объекта и обновляют свойство `Name`.</span><span class="sxs-lookup"><span data-stu-id="c87cd-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="c87cd-118">Переменные копировать нельзя.</span><span class="sxs-lookup"><span data-stu-id="c87cd-118">You cannot copy variables.</span></span> <span data-ttu-id="c87cd-119">Если объект, такой как задача, использует переменные, необходимо повторно создать переменные в целевом пакете.</span><span class="sxs-lookup"><span data-stu-id="c87cd-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="c87cd-120">И напротив, при копировании всего пакета переменные пакета также копируются.</span><span class="sxs-lookup"><span data-stu-id="c87cd-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c87cd-121">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c87cd-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c87cd-122">Копирование объектов пакета</span><span class="sxs-lookup"><span data-stu-id="c87cd-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="c87cd-123">Копирование элементов проекта</span><span class="sxs-lookup"><span data-stu-id="c87cd-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="c87cd-124">Сохранение пакета в качестве шаблона пакета</span><span class="sxs-lookup"><span data-stu-id="c87cd-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
