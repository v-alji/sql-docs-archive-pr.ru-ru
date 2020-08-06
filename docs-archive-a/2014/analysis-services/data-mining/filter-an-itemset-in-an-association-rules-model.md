---
title: Фильтрация набора элементов в модели правил взаимосвязей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- filtering itemsets [Analysis Services]
- Mining Model Viewer [Analysis Services], itemsets
ms.assetid: 3ed919ea-8598-45d2-a4a0-b1b3357a4ab1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f841280a6dd39a5f824f2e6a10975b0f80ed0761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655433"
---
# <a name="filter-an-itemset-in-an-association-rules-model"></a><span data-ttu-id="1ec5d-102">Фильтрация набора элементов в модели ассоциативных правил</span><span class="sxs-lookup"><span data-stu-id="1ec5d-102">Filter an Itemset in an Association Rules Model</span></span>
  <span data-ttu-id="1ec5d-103">В службах [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]можно отфильтровать наборы элементов, отображаемые на вкладке **Наборы элементов** средства просмотра правил взаимосвязи ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="1ec5d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can filter the itemsets that are displayed in the **Itemsets** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer.</span></span>  
  
### <a name="to-filter-an-itemset"></a><span data-ttu-id="1ec5d-104">Фильтрация наборов элементов</span><span class="sxs-lookup"><span data-stu-id="1ec5d-104">To filter an itemset</span></span>  
  
1.  <span data-ttu-id="1ec5d-105">На вкладке **Средство просмотра моделей интеллектуального анализа** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]перейдите на вкладку **Наборы элементов** в **Средство просмотра правил взаимосвязи**.</span><span class="sxs-lookup"><span data-stu-id="1ec5d-105">On the **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Itemsets** tab of the **Association Rules Viewer**.</span></span>  
  
2.  <span data-ttu-id="1ec5d-106">Введите условие правила в поле **Фильтрация набора элементов** .</span><span class="sxs-lookup"><span data-stu-id="1ec5d-106">Enter a rule condition in the **Filter itemset** box.</span></span> <span data-ttu-id="1ec5d-107">Например, условием правила может быть «Туризм-1000 = существующий»</span><span class="sxs-lookup"><span data-stu-id="1ec5d-107">For example, a rule condition might be "Touring-1000 = existing"</span></span>  
  
3.  <span data-ttu-id="1ec5d-108">Нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="1ec5d-108">Click **Enter**.</span></span>  
  
 <span data-ttu-id="1ec5d-109">Наборы элементов теперь отфильтрованы, чтобы отображать только те наборы, которые содержат выбранные элементы.</span><span class="sxs-lookup"><span data-stu-id="1ec5d-109">The itemsets are now filtered to display only those itemsets that contain the selected items.</span></span> <span data-ttu-id="1ec5d-110">Поле нечувствительно к регистру.</span><span class="sxs-lookup"><span data-stu-id="1ec5d-110">The box is not case-sensitive.</span></span> <span data-ttu-id="1ec5d-111">Фильтры хранятся в памяти, чтобы из списка можно было выбрать старый фильтр.</span><span class="sxs-lookup"><span data-stu-id="1ec5d-111">Filters are stored in memory so that you can select an old filter from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec5d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ec5d-112">See Also</span></span>  
 [<span data-ttu-id="1ec5d-113">Задачи и инструкции средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="1ec5d-113">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
