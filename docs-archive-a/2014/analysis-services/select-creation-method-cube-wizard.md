---
title: Выбор метода создания (мастер кубов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667411"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="41d2b-102">Выберите метод построения (мастер кубов)</span><span class="sxs-lookup"><span data-stu-id="41d2b-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="41d2b-103">Страница **Выбор метода создания** позволяет задать метод создания куба.</span><span class="sxs-lookup"><span data-stu-id="41d2b-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41d2b-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="41d2b-104">Options</span></span>  
 <span data-ttu-id="41d2b-105">**Использовать существующие таблицы**</span><span class="sxs-lookup"><span data-stu-id="41d2b-105">**Use existing tables**</span></span>  
 <span data-ttu-id="41d2b-106">Выберите этот параметр, чтобы создать куб с использованием таблиц, существующих в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="41d2b-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="41d2b-107">При построении нового куба мастер предоставит вам последовательные рекомендации по процессу выбора и определения групп мер и измерений, основанных на существующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="41d2b-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="41d2b-108">**Создать пустой куб**</span><span class="sxs-lookup"><span data-stu-id="41d2b-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="41d2b-109">Позволяет создать пустой куб.</span><span class="sxs-lookup"><span data-stu-id="41d2b-109">Select to create an empty cube.</span></span> <span data-ttu-id="41d2b-110">Этот параметр используется при необходимости создания вручную либо когда все группы мер куба являются связанными группами мер.</span><span class="sxs-lookup"><span data-stu-id="41d2b-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41d2b-111">Этот параметр доступен только при работе с проектом служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и отсутствии прямого подключения к базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41d2b-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="41d2b-112">**Создать таблицы в источнике данных**</span><span class="sxs-lookup"><span data-stu-id="41d2b-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="41d2b-113">Позволяет сначала создать куб, а затем на основе его определения создать в источнике данных новые таблицы.</span><span class="sxs-lookup"><span data-stu-id="41d2b-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41d2b-114">Чтобы использовать этот параметр, необходимо иметь разрешение на создание объектов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="41d2b-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="41d2b-115">При выборе этого параметра становится доступным параметр **Шаблон** .</span><span class="sxs-lookup"><span data-stu-id="41d2b-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="41d2b-116">**Шаблон**</span><span class="sxs-lookup"><span data-stu-id="41d2b-116">**Template**</span></span>  
 <span data-ttu-id="41d2b-117">Выберите шаблон, используемый для создания куба.</span><span class="sxs-lookup"><span data-stu-id="41d2b-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="41d2b-118">Шаблоны предоставляют набор определений, ориентированных на конкретную бизнес-задачу.</span><span class="sxs-lookup"><span data-stu-id="41d2b-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41d2b-119">Этот параметр доступен, только если выбран параметр **Создать таблицы в источнике данных** .</span><span class="sxs-lookup"><span data-stu-id="41d2b-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d2b-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="41d2b-120">See Also</span></span>  
 <span data-ttu-id="41d2b-121">[Объекты куба &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="41d2b-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="41d2b-122">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="41d2b-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="41d2b-123">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="41d2b-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
