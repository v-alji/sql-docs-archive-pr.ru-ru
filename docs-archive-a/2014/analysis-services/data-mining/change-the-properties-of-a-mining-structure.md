---
title: Изменение свойств структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727482"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="56924-102">изменить свойства структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="56924-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="56924-103">Имеется два вида свойств структур интеллектуального анализа данных (свойства обоих видов могут изменяться):</span><span class="sxs-lookup"><span data-stu-id="56924-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="56924-104">Свойства структуры интеллектуального анализа данных, влияющие на структуру в целом</span><span class="sxs-lookup"><span data-stu-id="56924-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="56924-105">Свойства отдельных столбцов в структуре</span><span class="sxs-lookup"><span data-stu-id="56924-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="56924-106">Учтите, что некоторые свойства зависят от значений других свойств.</span><span class="sxs-lookup"><span data-stu-id="56924-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="56924-107">Например, нельзя задать свойства, управляющие сегментированием (например, <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> или <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>), пока тип данных столбца не будет установлен в значение `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="56924-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="56924-108">Дополнительные сведения о свойствах структур интеллектуального анализа данных см. в разделе [Столбцы структуры интеллектуального анализа данных](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="56924-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="56924-109">Изменение свойств структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="56924-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="56924-110">На вкладке **Структура интеллектуального анализа данных** конструктора интеллектуального анализа данных щелкните правой кнопкой мыши структуру интеллектуального анализа данных или столбец в такой структуре, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="56924-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="56924-111">В правой части экрана появится окно **Свойства** , если оно еще не было открыто.</span><span class="sxs-lookup"><span data-stu-id="56924-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="56924-112">В окне **Свойства** выберите значение, соответствующее свойству, которое нужно изменить, и введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="56924-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="56924-113">Новое значение вступает в силу после выбора другого элемента в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="56924-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56924-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="56924-114">See Also</span></span>  
 [<span data-ttu-id="56924-115">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="56924-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
