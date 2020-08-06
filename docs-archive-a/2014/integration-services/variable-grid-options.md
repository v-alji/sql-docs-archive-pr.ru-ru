---
title: Параметры сетки переменных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656451"
---
# <a name="variable-grid-options"></a><span data-ttu-id="f0833-102">Параметры сетки переменных</span><span class="sxs-lookup"><span data-stu-id="f0833-102">Variable Grid Options</span></span>
  <span data-ttu-id="f0833-103">Используйте диалоговое окно **Параметры сетки переменных** для выбора столбцов, которые появятся в окне **Переменные** , и для выбора фильтров, применяемых к списку переменных.</span><span class="sxs-lookup"><span data-stu-id="f0833-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="f0833-104">Дополнительные сведения о свойствах соответствующей переменной см. в разделе [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f0833-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="f0833-105">Параметры фильтрации</span><span class="sxs-lookup"><span data-stu-id="f0833-105">Options for Filter</span></span>  
 <span data-ttu-id="f0833-106">**Отображать системные переменные**</span><span class="sxs-lookup"><span data-stu-id="f0833-106">**Show system variables**</span></span>  
 <span data-ttu-id="f0833-107">Выберите, чтобы в окне **Переменные** отображались системные переменные.</span><span class="sxs-lookup"><span data-stu-id="f0833-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="f0833-108">Системные переменные — это стандартные переменные.</span><span class="sxs-lookup"><span data-stu-id="f0833-108">System variables are predefined.</span></span> <span data-ttu-id="f0833-109">Системные переменные нельзя добавить или удалить.</span><span class="sxs-lookup"><span data-stu-id="f0833-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="f0833-110">Можно изменить параметр свойства **RaiseChangedEvent** .</span><span class="sxs-lookup"><span data-stu-id="f0833-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="f0833-111">В списке используется цветовой код.</span><span class="sxs-lookup"><span data-stu-id="f0833-111">This list is color coded.</span></span> <span data-ttu-id="f0833-112">Системные переменные отображаются серым цветом, а пользовательские — черным.</span><span class="sxs-lookup"><span data-stu-id="f0833-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="f0833-113">**Показывать переменные из всех областей видимости**</span><span class="sxs-lookup"><span data-stu-id="f0833-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="f0833-114">Выберите для отображения переменных из области видимости пакета и из областей видимости контейнеров, задач и обработчиков событий, находящихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="f0833-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="f0833-115">Оставьте этот параметр не выбранным, если следует показывать только переменные из области пакета и из области выбранного контейнера, задачи или обработчика события.</span><span class="sxs-lookup"><span data-stu-id="f0833-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="f0833-116">Дополнительные сведения об области переменной см. в разделе [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f0833-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="f0833-117">Параметры столбцов</span><span class="sxs-lookup"><span data-stu-id="f0833-117">Options for Columns</span></span>  
 <span data-ttu-id="f0833-118">Выберите столбцы, которые должны отображаться в окне **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="f0833-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="f0833-119">**Область**</span><span class="sxs-lookup"><span data-stu-id="f0833-119">**Scope**</span></span>  
  
-   <span data-ttu-id="f0833-120">**Data type**</span><span class="sxs-lookup"><span data-stu-id="f0833-120">**Data type**</span></span>  
  
-   <span data-ttu-id="f0833-121">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f0833-121">**Value**</span></span>  
  
-   <span data-ttu-id="f0833-122">**Пространство имен**</span><span class="sxs-lookup"><span data-stu-id="f0833-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="f0833-123">**Создавать событие при изменении значения переменной**</span><span class="sxs-lookup"><span data-stu-id="f0833-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="f0833-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f0833-124">**Description**</span></span>  
  
-   <span data-ttu-id="f0833-125">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="f0833-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0833-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0833-126">See Also</span></span>  
 <span data-ttu-id="f0833-127">[Окно переменных](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="f0833-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="f0833-128">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="f0833-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="f0833-129">[Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="f0833-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="f0833-130">Обработчики событий в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="f0833-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
