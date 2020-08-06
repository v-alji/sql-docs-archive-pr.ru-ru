---
title: Обработка модели кластеризации последовательностей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4a7545fd-37a3-4766-ad59-0946f1bd3524
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9975105fb6779e150e3a498bc87654d21292a1b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735617"
---
# <a name="processing-the-sequence-clustering-model"></a><span data-ttu-id="26986-102">Обработка модели кластеризации последовательностей</span><span class="sxs-lookup"><span data-stu-id="26986-102">Processing the Sequence Clustering Model</span></span>
  <span data-ttu-id="26986-103">После создания новой структуры интеллектуального анализа данных необходимо выполнить развертывание изменений, внесенных в решение интеллектуального анализа данных, а затем обработать структуру.</span><span class="sxs-lookup"><span data-stu-id="26986-103">After you create a new mining structure, you must deploy the changes that you made to the data mining solution, and then process the structure.</span></span> <span data-ttu-id="26986-104">После завершения обработки новой структуры и модели интеллектуального анализа данных можно просмотреть модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="26986-104">After processing of both the new structure and the mining model is complete, you can browse the mining model.</span></span>  
  
 <span data-ttu-id="26986-105">Обработка всегда обязательна, если была создана новая структура интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="26986-105">Processing is always required when you create a new data mining structure.</span></span> <span data-ttu-id="26986-106">Однако при добавлении новой модели интеллектуального анализа данных к существующей структуре можно выполнить только обработку модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="26986-106">However, if you add a new mining model to an existing structure, you can process just the mining model.</span></span> <span data-ttu-id="26986-107">В этом сценарии, поскольку были созданы новая структура интеллектуального анализа данных и новая модель интеллектуального анализа данных, придется обработать и структуру, и модель.</span><span class="sxs-lookup"><span data-stu-id="26986-107">In this scenario, because you have created a new mining structure and a new mining model, you must process both.</span></span>  
  
### <a name="to-process-the-mining-structure-and-model"></a><span data-ttu-id="26986-108">Обработка структуры и модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="26986-108">To process the mining structure and model</span></span>  
  
1.  <span data-ttu-id="26986-109">В меню **Модель интеллектуального анализа данных** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите команду **Обработать структуру интеллектуального анализа данных и все модели**.</span><span class="sxs-lookup"><span data-stu-id="26986-109">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models**.</span></span>  
  
2.  <span data-ttu-id="26986-110">В окне предупреждения с вопросом о том, нужно ли выполнить построение и развертывание проекта, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="26986-110">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="26986-111">В диалоговом окне **Обработка структуры интеллектуального анализа данных — кластеризация последовательностей по регионам** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="26986-111">In the **Process Mining Structure - Sequence Clustering with Region** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="26986-112">Будет открыто диалоговое окно **Ход обработки** , в котором отображаются сведения о ходе обработки модели.</span><span class="sxs-lookup"><span data-stu-id="26986-112">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="26986-113">Обработка новой структуры и модели может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="26986-113">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="26986-114">После успешного завершения обработки нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Ход обработки** .</span><span class="sxs-lookup"><span data-stu-id="26986-114">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="26986-115">Затем нажмите кнопку **Закрыть** в диалоговом окне **Обработка структуры интеллектуального анализа данных — кластеризация последовательностей по регионам** .</span><span class="sxs-lookup"><span data-stu-id="26986-115">Click **Close** again to exit the **Process Mining Structure - Sequence Clustering with Region** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="26986-116">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="26986-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="26986-117">Изучение модели кластеризации последовательностей &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="26986-117">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="26986-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="26986-118">See Also</span></span>  
 <span data-ttu-id="26986-119">[Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="26986-119">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 <span data-ttu-id="26986-120">[Алгоритм кластеризации последовательностей (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="26986-120">[Microsoft Sequence Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="26986-121">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="26986-121">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
