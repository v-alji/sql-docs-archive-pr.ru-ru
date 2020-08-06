---
title: Редактор преобразования "Отмена свертывания" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656454"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="fcb0c-102">Редактор преобразования «Отмена свертывания»</span><span class="sxs-lookup"><span data-stu-id="fcb0c-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="fcb0c-103">Используйте диалоговое окно **Редактор преобразования «Отмена свертывания»** , чтобы выбрать столбцы для сведения в строки, а также указать столбцы данных и новый выходной столбец сведенных значений.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcb0c-104"> Этот раздел опирается на сценарий отмены свертывания, описанный в разделе [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) , чтобы проиллюстрировать использование параметров.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="fcb0c-105">Дополнительные сведения о преобразовании отмены свертывания см. в разделе [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fcb0c-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fcb0c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcb0c-106">Options</span></span>  
 <span data-ttu-id="fcb0c-107">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="fcb0c-108">Используя флажки, укажите столбцы, которые должны быть сведены в строки.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="fcb0c-109">**имя**;</span><span class="sxs-lookup"><span data-stu-id="fcb0c-109">**Name**</span></span>  
 <span data-ttu-id="fcb0c-110">Просмотрите имя доступного входного столбца.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="fcb0c-111">**Передать**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-111">**Pass Through**</span></span>  
 <span data-ttu-id="fcb0c-112">Укажите, следует ли включить этот столбец в выход с отмененным сведением.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="fcb0c-113">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-113">**Input Column**</span></span>  
 <span data-ttu-id="fcb0c-114">Выберите для каждой строки столбец из списка доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="fcb0c-115">Выбранные столбцы обозначаются флажками в таблице **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="fcb0c-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="fcb0c-116">В сценарии отмены свертывания, описанном в разделе [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), входными столбцами являлись столбцы **Ham**, **Soda**, **Milk**, **Beer**и **Chips** .</span><span class="sxs-lookup"><span data-stu-id="fcb0c-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="fcb0c-117">**Целевой столбец**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-117">**Destination Column**</span></span>  
 <span data-ttu-id="fcb0c-118">Введите имя столбца данных.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="fcb0c-119">В сценарии отмены свертывания, описанном в разделе [Преобразование отмены свертывания](data-flow/transformations/unpivot-transformation.md), целевым столбцом является столбец количества (**Qty**).</span><span class="sxs-lookup"><span data-stu-id="fcb0c-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="fcb0c-120">**Значение ключа сведения**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="fcb0c-121">Введите имя значения сведения.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="fcb0c-122">По умолчанию, используется имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="fcb0c-123">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="fcb0c-124">В сценарии отмены свертывания, описанном в разделе [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), значения сведения представлены в новом столбце Product, обозначенном параметром **Имя столбца значений ключа сведения** , в виде текстовых значений **Ham**, **Soda**, **Milk**, **Beer**и **Chips**.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="fcb0c-125">**Имя столбца значений ключа сведения**</span><span class="sxs-lookup"><span data-stu-id="fcb0c-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="fcb0c-126">Введите имя столбца значений ключа сведения.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="fcb0c-127">По умолчанию, используется «Значение ключа сведения», тем не менее можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="fcb0c-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="fcb0c-128">В сценарии отмены свертывания, описанном в разделе [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), именем столбца значений ключа сведения является **Product** , оно обозначает новый столбец **Product** , в который осуществляется отмена свертывания столбцов **Ham**, **Soda**, **Milk**, **Beer**и **Chips** .</span><span class="sxs-lookup"><span data-stu-id="fcb0c-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb0c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcb0c-129">See Also</span></span>  
 <span data-ttu-id="fcb0c-130">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fcb0c-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="fcb0c-131">Преобразование "Сведение"</span><span class="sxs-lookup"><span data-stu-id="fcb0c-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
