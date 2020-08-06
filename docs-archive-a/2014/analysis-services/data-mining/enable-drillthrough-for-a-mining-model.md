---
title: Включить детализацию для модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655431"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="ff013-102">включить детализацию для модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff013-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="ff013-103">Если в модели интеллектуального анализа данных включена детализация, то при просмотре модели можно извлекать подробные сведения о вариантах, использованных при создании модели.</span><span class="sxs-lookup"><span data-stu-id="ff013-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="ff013-104">Для просмотра этой информации необходимо иметь соответствующие разрешения. Структура к моменту просмотра должна быть уже обработана.</span><span class="sxs-lookup"><span data-stu-id="ff013-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="ff013-105">**Разрешения** . Чтобы пользователь мог детализировать данные модели или структуры, он должен быть членом роли, имеющей разрешения [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) в отношении такой модели или структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff013-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="ff013-106">Разрешения на детализацию устанавливаются отдельно для структуры и для модели.</span><span class="sxs-lookup"><span data-stu-id="ff013-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="ff013-107">Разрешения на детализацию модели позволяют проводить детализацию на основе модели даже при отсутствии разрешений на детализацию структуры.</span><span class="sxs-lookup"><span data-stu-id="ff013-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="ff013-108">Разрешения на детализацию структуры предоставляют дополнительную возможность включать столбцы структуры в запросы детализации с помощью функции [StructureColumn (DMX)](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="ff013-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="ff013-109">Вы также можете запрашивать обучающие и тестовые варианты в структуре с помощью инструкции SELECT... ИЗ \<structure> . Синтаксис вариантов.</span><span class="sxs-lookup"><span data-stu-id="ff013-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="ff013-110">**Кэширование обучающих вариантов** . Детализация работает посредством получения информации об обучающих вариантах в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff013-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="ff013-111">При обработке структуры эта информация кэшируется.</span><span class="sxs-lookup"><span data-stu-id="ff013-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="ff013-112">Поэтому, если произвести удаление всех кэшированных данных путем изменения свойства <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> на `ClearAfterProcessing`, детализация работать не будет.</span><span class="sxs-lookup"><span data-stu-id="ff013-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff013-113">Если обучающие варианты не кэшированы, для просмотра данных варианта нужно сначала изменить свойство <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> на **KeepTrainingCases** , а затем провести повторную обработку модели.</span><span class="sxs-lookup"><span data-stu-id="ff013-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="ff013-114">Дополнительные сведения см. в разделе [Запросы детализации (интеллектуальный анализ данных)](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ff013-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="ff013-115">Включение детализации в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff013-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="ff013-116">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]на вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных щелкните правой кнопкой мыши модель интеллектуального анализа данных, для которой нужно включить детализацию, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ff013-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ff013-117">В окнах **свойств** щелкните **AllowDrillthrough**и выберите **значение true**.</span><span class="sxs-lookup"><span data-stu-id="ff013-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="ff013-118">На вкладке **Модели интеллектуального анализа данных** щелкните правой кнопкой мыши нужную модель и выберите команду **Обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="ff013-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="ff013-119">Включение кэширования для структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff013-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="ff013-120">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]на вкладке **Структура интеллектуального анализа данных** конструктора интеллектуального анализа данных щелкните правой кнопкой мыши имя структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff013-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="ff013-121">Откройте окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="ff013-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="ff013-122">В окне **Свойства** найдите свойство **CacheMode** , а затем выберите **KeepTrainingCases** из списка.</span><span class="sxs-lookup"><span data-stu-id="ff013-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="ff013-123">В меню **База данных** выберите **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="ff013-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff013-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff013-124">See Also</span></span>  
 [<span data-ttu-id="ff013-125">Запросы детализации (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="ff013-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
