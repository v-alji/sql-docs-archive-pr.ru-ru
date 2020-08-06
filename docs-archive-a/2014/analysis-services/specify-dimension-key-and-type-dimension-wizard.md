---
title: Указание ключа и типа измерения (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666782"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="4d04b-102">Указание ключа и типа измерения (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="4d04b-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="4d04b-103">На странице **Определение ключа и типа измерения** можно определить ключевой атрибут измерения и указать, является ли измерение медленно меняющимся измерением (SCD).</span><span class="sxs-lookup"><span data-stu-id="4d04b-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d04b-104"> Эта страница отображается, только если на странице **Выбор метода построения** выбран параметр **Построить измерение без использования источника данных** и если на странице **Выбор типа измерения** выбрано **Стандартное измерение** .</span><span class="sxs-lookup"><span data-stu-id="4d04b-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d04b-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="4d04b-105">Options</span></span>  
 <span data-ttu-id="4d04b-106">**Ключевой атрибут**</span><span class="sxs-lookup"><span data-stu-id="4d04b-106">**Key attribute**</span></span>  
 <span data-ttu-id="4d04b-107">Выберите атрибут, который будет ключевым атрибутом для измерения.</span><span class="sxs-lookup"><span data-stu-id="4d04b-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d04b-108">Если для измерения не определены никакие атрибуты, единственным значением, доступным для этого параметра, является **Создать ключевой атрибут автоматически**</span><span class="sxs-lookup"><span data-stu-id="4d04b-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="4d04b-109">. Это значение недоступно, если для измерения определены какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4d04b-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="4d04b-110">**Это изменяющееся измерение**</span><span class="sxs-lookup"><span data-stu-id="4d04b-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="4d04b-111">Этот параметр указывает, что измерение является медленно меняющимся измерением.</span><span class="sxs-lookup"><span data-stu-id="4d04b-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="4d04b-112">При выборе этого параметра создаются новые столбцы и атрибуты, которые могут использоваться для отслеживания перемещения элементов в иерархиях измерения с течением времени.</span><span class="sxs-lookup"><span data-stu-id="4d04b-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d04b-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d04b-113">See Also</span></span>  
 <span data-ttu-id="4d04b-114">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4d04b-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="4d04b-115">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4d04b-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4d04b-116">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="4d04b-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
