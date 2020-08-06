---
title: Основные сведения о пакете служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734317"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="fb2fd-102">Основы работы с пакетами служб SSIS</span><span class="sxs-lookup"><span data-stu-id="fb2fd-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="fb2fd-103">Пакет представляет собой объект, который реализует функциональность служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] по извлечению, преобразованию и загрузке данных.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="fb2fd-104">Пакет создается с помощью конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb2fd-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="fb2fd-105">Его можно также создать с помощью мастера импорта и экспорта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] либо мастера проекта соединений служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb2fd-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="fb2fd-106">Для получения дополнительных сведений [Создайте пакеты в SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) в КОНСТРУКТОРЕ служб SSIS и [мастере импорта проектов](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fb2fd-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="fb2fd-107">Основной пакет включает следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="fb2fd-108">**Элементы потока управления**</span><span class="sxs-lookup"><span data-stu-id="fb2fd-108">**Control flow elements**</span></span>  
 <span data-ttu-id="fb2fd-109">Эти обязательные элементы выполняют различные функции, поддерживают структуру и управляют порядком выполнения элементов.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="fb2fd-110">Основными элементами потока управления являются задачи, контейнеры и управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="fb2fd-111">В пакете должен быть по крайней мере один элемент потока управления.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="fb2fd-112">Дополнительные сведения см. в разделе [Поток управления](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="fb2fd-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="fb2fd-113">**Элементы потока данных**</span><span class="sxs-lookup"><span data-stu-id="fb2fd-113">**Data flow elements**</span></span>  
 <span data-ttu-id="fb2fd-114">Эти необязательные элементы извлекают, изменяют и загружают данные в источники данных.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="fb2fd-115">Основными элементами потока данных являются источники, преобразования и назначения.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="fb2fd-116">Присутствие каких-либо элементов потока данных в пакете необязательно.</span><span class="sxs-lookup"><span data-stu-id="fb2fd-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="fb2fd-117">Дополнительные сведения см. в статье [Поток данных](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="fb2fd-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="fb2fd-118">Пример создания базового пакета см. [в разделе занятие 1. Создание проекта и основного пакета](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="fb2fd-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fb2fd-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fb2fd-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fb2fd-120">Создание пакетов в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="fb2fd-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="fb2fd-121">Добавление задачи или контейнера в поток управления или удалить их из него</span><span class="sxs-lookup"><span data-stu-id="fb2fd-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="fb2fd-122">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="fb2fd-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="fb2fd-123">Добавление или удаление компонента в потоке данных</span><span class="sxs-lookup"><span data-stu-id="fb2fd-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="fb2fd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fb2fd-124">Related Content</span></span>  
  
1.  <span data-ttu-id="fb2fd-125">Видеоматериал [Создание основного пакета (видеоматериал SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131023)на сайте MSDN.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fb2fd-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2fd-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb2fd-126">See Also</span></span>  
 <span data-ttu-id="fb2fd-127">[Integration Services &#40;пакетов&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="fb2fd-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="fb2fd-128">Управление очередностью</span><span class="sxs-lookup"><span data-stu-id="fb2fd-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
