---
title: Диалоговое окно «Привязка объекта» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665608"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="62b8e-102">Диалоговое окно «Привязка объектов»</span><span class="sxs-lookup"><span data-stu-id="62b8e-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="62b8e-103">Используйте диалоговое окно **Привязка объекта** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для определения привязок между свойством объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и таблицей или столбцом в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="62b8e-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="62b8e-104">Диалоговое окно **Привязка объектов** можно открыть, выбрав пункт **(создать)** из раскрывающегося списка для значения следующих свойств объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в окне **Свойства** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="62b8e-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="62b8e-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="62b8e-105">NameColumn</span></span>  
  
-   <span data-ttu-id="62b8e-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="62b8e-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="62b8e-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="62b8e-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="62b8e-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="62b8e-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="62b8e-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="62b8e-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="62b8e-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="62b8e-110">Options</span></span>  
 <span data-ttu-id="62b8e-111">**Тип привязки**</span><span class="sxs-lookup"><span data-stu-id="62b8e-111">**Binding type**</span></span>  
 <span data-ttu-id="62b8e-112">Выбирает привязку для использования с объектом служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62b8e-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="62b8e-113">Можно использовать следующие типы привязки:</span><span class="sxs-lookup"><span data-stu-id="62b8e-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="62b8e-114">Привязка к столбцу</span><span class="sxs-lookup"><span data-stu-id="62b8e-114">Column binding</span></span>  
 <span data-ttu-id="62b8e-115">Привязывает объект к существующей таблице и столбцу в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="62b8e-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="62b8e-116">Сформировать столбец</span><span class="sxs-lookup"><span data-stu-id="62b8e-116">Generate column</span></span>  
 <span data-ttu-id="62b8e-117">Указывает, что в представлении источника данных следует определить новый столбец и ассоциировать с ним привязку к столбцу.</span><span class="sxs-lookup"><span data-stu-id="62b8e-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b8e-118">Если выбран этот параметр, необходимо запустить **мастер формирования схем** до развертывания объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62b8e-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="62b8e-119">Привязка строк</span><span class="sxs-lookup"><span data-stu-id="62b8e-119">Row binding</span></span>  
 <span data-ttu-id="62b8e-120">Привязывает объект к строке в таблице фактов и используется для облегчения подсчета мер на основе количества строк, обработанных в таблице фактов.</span><span class="sxs-lookup"><span data-stu-id="62b8e-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="62b8e-121">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="62b8e-121">**Source table**</span></span>  
 <span data-ttu-id="62b8e-122">Выводит список таблиц в представлении источника данных, ассоциированном с объектом служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62b8e-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="62b8e-123">**Исходный столбец**</span><span class="sxs-lookup"><span data-stu-id="62b8e-123">**Source column**</span></span>  
 <span data-ttu-id="62b8e-124">Выводит список столбцов в таблице, выбранной в параметре **Исходная таблица**.</span><span class="sxs-lookup"><span data-stu-id="62b8e-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b8e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="62b8e-125">See Also</span></span>  
 [<span data-ttu-id="62b8e-126">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="62b8e-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
