---
title: Удаление фильтра из модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656041"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="37902-102">удалить фильтр из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="37902-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="37902-103">При создании фильтра для модели интеллектуального анализа можно создавать модели для подмножества данных в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="37902-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="37902-104">Фильтры также полезны при тестировании точности модели на подмножестве исходных данных.</span><span class="sxs-lookup"><span data-stu-id="37902-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="37902-105">Однако если потребуется снова рассмотреть полное множество вариантов, необходимо будет удалить этот фильтр.</span><span class="sxs-lookup"><span data-stu-id="37902-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="37902-106">Эта процедура описывает удаление условий фильтра и фильтра полностью.</span><span class="sxs-lookup"><span data-stu-id="37902-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="37902-107">Удаление условия фильтра модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="37902-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="37902-108">В обозревателе решений [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните структуру интеллектуального анализа данных, содержащую ту модель интеллектуального анализа данных, к которой нужно применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="37902-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="37902-109">Перейдите на вкладку **Модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="37902-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="37902-110">Выберите модель и щелкните правой кнопкой мыши, чтобы открыть контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="37902-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="37902-111">-или-</span><span class="sxs-lookup"><span data-stu-id="37902-111">-or-</span></span>  
  
     <span data-ttu-id="37902-112">Выберите модель.</span><span class="sxs-lookup"><span data-stu-id="37902-112">Select the model.</span></span> <span data-ttu-id="37902-113">В меню **Модель интеллектуального анализа данных** выберите команду **Установить фильтр моделей**.</span><span class="sxs-lookup"><span data-stu-id="37902-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="37902-114">В диалоговом окне **Фильтр модели** щелкните правой кнопкой строку в сетке, которая содержит условие, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="37902-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="37902-115">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="37902-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="37902-116">Очистка фильтра модели интеллектуального анализа данных в диалоговом окне «Редактор фильтров»</span><span class="sxs-lookup"><span data-stu-id="37902-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="37902-117">В диалоговом окне **Редактор фильтров** щелкните правой кнопкой мыши любую строку в сетке и выберите команду **Удалить все**.</span><span class="sxs-lookup"><span data-stu-id="37902-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="37902-118">Работа с фильтрами моделей с помощью окна «Свойства»</span><span class="sxs-lookup"><span data-stu-id="37902-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="37902-119">Если нужно удалить весь фильтр, нет необходимости открывать диалоговые окна редактора фильтра.</span><span class="sxs-lookup"><span data-stu-id="37902-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="37902-120">Созданные условия фильтра доступны в свойстве `Filter` модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="37902-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37902-121">Свойства модели интеллектуального анализа данных можно просматривать в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], но не в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37902-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="37902-122">Очистка фильтра модели интеллектуального анализа данных в обозревателе решений</span><span class="sxs-lookup"><span data-stu-id="37902-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="37902-123">В обозревателе решений щелкните модель интеллектуального анализа данных, содержащую фильтр.</span><span class="sxs-lookup"><span data-stu-id="37902-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="37902-124">В окне **Свойства** щелкните правой кнопкой мыши текст фильтра в `Filter` свойстве и выберите **команду выбрать все**.</span><span class="sxs-lookup"><span data-stu-id="37902-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="37902-125">Нажмите клавишу "BACKSPACE" или "DELETE".</span><span class="sxs-lookup"><span data-stu-id="37902-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37902-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="37902-126">See Also</span></span>  
 <span data-ttu-id="37902-127">[Детализация до данных вариантов из модели интеллектуального анализа данных](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="37902-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="37902-128">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="37902-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="37902-129">Фильтры для моделей интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="37902-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
