---
title: Изменение дискретизации столбца в модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667494"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="bc112-102">изменить дискретизацию столбца в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bc112-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="bc112-103">автоматически дискретизировать значения, то есть данные ячеек в числовом столбце — в определенных сценариях.</span><span class="sxs-lookup"><span data-stu-id="bc112-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="bc112-104">Например, если в данных содержатся непрерывные числовые данные и создается модель дерева принятия решений, каждый столбец непрерывных данных автоматически будет сегментирован (в зависимости от распределения данных).</span><span class="sxs-lookup"><span data-stu-id="bc112-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="bc112-105">Если вам необходимо управлять процессом дискретизации данных, измените свойства столбца структуры интеллектуального анализа данных, управляющие использованием данных в модели.</span><span class="sxs-lookup"><span data-stu-id="bc112-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="bc112-106">Общие сведения о задании свойств в модели интеллектуального анализа данных см. в разделе [Столбцы модели интеллектуального анализа данных](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="bc112-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="bc112-107">Отображение свойств столбца модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bc112-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="bc112-108">На вкладке **Модели интеллектуального анализа данных** в конструкторе интеллектуального анализа данных щелкните правой кнопкой мыши либо заголовок столбца, содержащего имя модели интеллектуального анализа данных, либо строку сетки, содержащую имя алгоритма. Потом выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bc112-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="bc112-109">В окне **Свойства** отображаются свойства, связанные с моделью интеллектуального анализа данных в целом.</span><span class="sxs-lookup"><span data-stu-id="bc112-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="bc112-110">В столбце **Структура** , расположенном на левой стороне экрана, щелкните по столбцу, содержащему подлежащие дискретизации непрерывные числовые данные.</span><span class="sxs-lookup"><span data-stu-id="bc112-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="bc112-111">Окно **Свойства** изменится и будет отображать только те свойства, которые связаны с выбранным столбцом.</span><span class="sxs-lookup"><span data-stu-id="bc112-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="bc112-112">Изменение метода дискретизации</span><span class="sxs-lookup"><span data-stu-id="bc112-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="bc112-113">В окне **Свойства интеллектуального анализа данных** щелкните текстовое поле рядом с **содержимым**и выберите `Discretized` из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bc112-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="bc112-114">В окне <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> и <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> включены.</span><span class="sxs-lookup"><span data-stu-id="bc112-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="bc112-115">В окне **Свойства** щелкните текстовое поле рядом с полем <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> и выберите одно из следующих значений: `Automatic` , `EqualAreas` или `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="bc112-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc112-116">Если для столбца задано значение `Ignore` , окно **свойств** столбца остается пустым.</span><span class="sxs-lookup"><span data-stu-id="bc112-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="bc112-117">Новое значение вступает в силу после выбора другого элемента в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="bc112-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="bc112-118">На вкладке **Свойства** щелкните по текстовому полю <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> и введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="bc112-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc112-119">После изменения данных свойств необходимо выполнить повторную обработку структуры и всех моделей, для которых должны действовать новые настройки.</span><span class="sxs-lookup"><span data-stu-id="bc112-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc112-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc112-120">See Also</span></span>  
 [<span data-ttu-id="bc112-121">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bc112-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
