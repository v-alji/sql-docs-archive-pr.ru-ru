---
title: Окно "Свойства" (среда Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- sorting properties [SQL Server]
- Properties window [SQL Server Management Studio]
- modifying properties
ms.assetid: 6a9a1389-df8d-4cfc-928b-eccbf884a22d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 33a48ef65a29823abb2e9757575ed006c309969b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727850"
---
# <a name="properties-window-management-studio"></a><span data-ttu-id="d4962-102">Окно «Свойства» (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d4962-102">Properties Window (Management Studio)</span></span>
  <span data-ttu-id="d4962-103">Это окно используется для просмотра свойств выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="d4962-103">Use this window to view properties of selected elements.</span></span> <span data-ttu-id="d4962-104">Кроме того, в окне «Свойства» можно просматривать свойства файла, проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="d4962-104">You can also use the Properties window to view file, project, and solution properties.</span></span> <span data-ttu-id="d4962-105">Чтобы открыть окно «Свойства», щелкните **Окно «Свойства»** в меню **Вид** .</span><span class="sxs-lookup"><span data-stu-id="d4962-105">The Properties window is available by clicking **Properties Window** on the **View** menu.</span></span>  
  
 <span data-ttu-id="d4962-106">В окне «Свойства» в зависимости от особенностей конкретного свойства могут отображаться различные типы изменяемых полей.</span><span class="sxs-lookup"><span data-stu-id="d4962-106">The Properties window displays different types of editing fields, depending on the needs of a particular property.</span></span> <span data-ttu-id="d4962-107">Свойства, выделенные серым цветом, доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d4962-107">Properties shown in gray are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4962-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4962-108">Options</span></span>  
  
|<span data-ttu-id="d4962-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="d4962-109">Element</span></span>|<span data-ttu-id="d4962-110">Description</span><span class="sxs-lookup"><span data-stu-id="d4962-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4962-111">**Имя объекта**</span><span class="sxs-lookup"><span data-stu-id="d4962-111">**Object name**</span></span>|<span data-ttu-id="d4962-112">Приводит список выбранных объектов.</span><span class="sxs-lookup"><span data-stu-id="d4962-112">Lists the currently selected object or objects.</span></span> <span data-ttu-id="d4962-113">Отображаются только объекты активного редактора или конструктора.</span><span class="sxs-lookup"><span data-stu-id="d4962-113">Only objects from the active editor or designer are visible.</span></span>|  
|<span data-ttu-id="d4962-114">**По категориям**</span><span class="sxs-lookup"><span data-stu-id="d4962-114">**Categorized**</span></span>|<span data-ttu-id="d4962-115">Перечисляются все свойства и их значения для выбранного объекта по категориям.</span><span class="sxs-lookup"><span data-stu-id="d4962-115">Lists all properties and property values for the selected object, by category.</span></span> <span data-ttu-id="d4962-116">Чтобы сократить количество отображаемых свойств, можно свернуть категорию.</span><span class="sxs-lookup"><span data-stu-id="d4962-116">You can collapse a category to reduce the number of visible properties.</span></span> <span data-ttu-id="d4962-117">При развертывании или свертывании категории слева от ее имени отображается знак «плюс» (+) или «минус» (-).</span><span class="sxs-lookup"><span data-stu-id="d4962-117">When you expand or collapse a category, you see a plus (+) or minus (-) to the left of the category name.</span></span> <span data-ttu-id="d4962-118">Категории перечислены в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="d4962-118">Categories are listed alphabetically.</span></span>|  
|<span data-ttu-id="d4962-119">**По алфавиту**</span><span class="sxs-lookup"><span data-stu-id="d4962-119">**Alphabetic**</span></span>|<span data-ttu-id="d4962-120">Все свойства и события для выбранных объектов, доступные при проектировании, сортируются по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="d4962-120">Alphabetically sorts all design-time properties and events for selected objects.</span></span>|  
|<span data-ttu-id="d4962-121">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="d4962-121">**Properties**</span></span>|<span data-ttu-id="d4962-122">Перечисляются свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="d4962-122">Displays the properties for an object.</span></span>|  
|<span data-ttu-id="d4962-123">**Панель описания**</span><span class="sxs-lookup"><span data-stu-id="d4962-123">**Description pane**</span></span>|<span data-ttu-id="d4962-124">панель описания расположена в нижней части окна «Свойства» и содержит тип и краткое описание текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="d4962-124">The description pane appears at the bottom of the Properties window and shows the property type and a short description of the property.</span></span> <span data-ttu-id="d4962-125">Для включения и отключения описания свойства можно использовать команду **Описание** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="d4962-125">You can turn the description of the property off and on using the **Description** command on the shortcut menu.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4962-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4962-126">See Also</span></span>  
 [<span data-ttu-id="d4962-127">Общие элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d4962-127">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
