---
title: Занятие 3. изменение мер, атрибутов и иерархий | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665646"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="303bb-102">Урок 3. Изменение мер, атрибутов и иерархий</span><span class="sxs-lookup"><span data-stu-id="303bb-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="303bb-103">После определения начального куба можно увеличить его полезность и удобство использования.</span><span class="sxs-lookup"><span data-stu-id="303bb-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="303bb-104">Это можно сделать, добавив иерархии, поддерживающие навигацию и агрегаты на разных уровнях, применив форматы к конкретной мере и определив вычисления и связи.</span><span class="sxs-lookup"><span data-stu-id="303bb-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="303bb-105">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="303bb-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="303bb-106">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="303bb-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="303bb-107">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="303bb-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="303bb-108">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="303bb-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="303bb-109">Изменение мер</span><span class="sxs-lookup"><span data-stu-id="303bb-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="303bb-110">В этой задаче предстоит указать свойства форматирования мер валюты и процентов в кубе учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="303bb-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="303bb-111">Изменение измерения «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="303bb-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="303bb-112">В этой задаче определяется пользовательская иерархия, создаются именованные вычисления, изменяются атрибуты для использования именованных вычислений, группируются атрибуты и пользовательские иерархии в папки отображения.</span><span class="sxs-lookup"><span data-stu-id="303bb-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="303bb-113">Изменение измерения Product</span><span class="sxs-lookup"><span data-stu-id="303bb-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="303bb-114">В этой задаче определяется пользовательская иерархия, создаются именованные вычисления, определяются имя элемента «Все» и папки отображения.</span><span class="sxs-lookup"><span data-stu-id="303bb-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="303bb-115">Изменение измерения Date</span><span class="sxs-lookup"><span data-stu-id="303bb-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="303bb-116">В этой задаче определяется пользовательская иерархия, изменяются имена элементов атрибута и используются составные ключи, чтобы указать уникальные элементы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="303bb-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="303bb-117">Просмотр развернутого куба</span><span class="sxs-lookup"><span data-stu-id="303bb-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="303bb-118">В этой задаче с помощью обозревателя в конструкторе кубов выполняется просмотр данных куба.</span><span class="sxs-lookup"><span data-stu-id="303bb-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303bb-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="303bb-119">See Also</span></span>  
 <span data-ttu-id="303bb-120">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="303bb-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="303bb-121">Многомерное моделирование (учебник по Adventure Works)</span><span class="sxs-lookup"><span data-stu-id="303bb-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
