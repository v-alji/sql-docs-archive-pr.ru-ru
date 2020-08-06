---
title: Обработка модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734609"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="a927f-102">обработать модель интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="a927f-102">Process a Mining Model</span></span>
  <span data-ttu-id="a927f-103">На вкладке «Модели интеллектуального анализа данных» конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]можно либо обработать конкретную модель, которая связана со структурой интеллектуального анализа данных, либо обработать все модели, связанные с этой структурой.</span><span class="sxs-lookup"><span data-stu-id="a927f-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="a927f-104">Обработка модели интеллектуального анализа данных производится с помощью следующих инструментов.</span><span class="sxs-lookup"><span data-stu-id="a927f-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="a927f-105">Для обработки также можно использовать команду XMLA Process.</span><span class="sxs-lookup"><span data-stu-id="a927f-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="a927f-106">Дополнительные сведения см. в разделе [Средства и способы обработки (службы Analysis Services)](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a927f-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="a927f-107">Обработка отдельной модели интеллектуального анализа данных с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="a927f-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="a927f-108">На вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных выберите модель интеллектуального анализа данных из одного или нескольких столбцов моделей в сетке.</span><span class="sxs-lookup"><span data-stu-id="a927f-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="a927f-109">В меню **Модель интеллектуального анализа данных** выберите пункт **Обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="a927f-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="a927f-110">При внесении изменений в структуру интеллектуального анализа данных будет выдано приглашение к повторному развертыванию структуры перед обработкой модели.</span><span class="sxs-lookup"><span data-stu-id="a927f-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="a927f-111">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a927f-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="a927f-112">В диалоговом окне **Обработка модели \<model> интеллектуального анализа данных** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a927f-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="a927f-113">Откроется диалоговое окно **Развитие процесса** , отображающее подробные сведения об обработке модели.</span><span class="sxs-lookup"><span data-stu-id="a927f-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="a927f-114">После успешного завершения обработки модели нажмите кнопку **Закрыть** в диалоговом окне **Развитие процесса** .</span><span class="sxs-lookup"><span data-stu-id="a927f-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="a927f-115">Нажмите кнопку **Закрыть** в диалоговом окне **Обработка \<model> модели интеллектуального анализа данных —** .</span><span class="sxs-lookup"><span data-stu-id="a927f-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="a927f-116">Были обработаны только структура интеллектуального анализа данных и выбранная модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a927f-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="a927f-117">Обработка всех моделей интеллектуального анализа данных, которые связаны со структурой интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="a927f-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="a927f-118">На вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных выберите команду **Обработать структуру интеллектуального анализа данных и все модели** из меню **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="a927f-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="a927f-119">При внесении изменений в структуру интеллектуального анализа данных будет выдано приглашение к повторному развертыванию структуры перед обработкой моделей.</span><span class="sxs-lookup"><span data-stu-id="a927f-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="a927f-120">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a927f-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="a927f-121">В диалоговом окне **Обработка структуры \<structure> интеллектуального анализа данных** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a927f-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="a927f-122">Откроется диалоговое окно **Развитие процесса** , отображающее подробные сведения об обработке модели.</span><span class="sxs-lookup"><span data-stu-id="a927f-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="a927f-123">После успешного завершения обработки моделей нажмите кнопку **Закрыть** в диалоговом окне **Развитие процесса** .</span><span class="sxs-lookup"><span data-stu-id="a927f-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="a927f-124">В диалоговом окне \*\*Обработка \<model> \*\* нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="a927f-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="a927f-125">Были обработаны структура интеллектуального анализа данных и все связанные с ней модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a927f-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a927f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a927f-126">See Also</span></span>  
 [<span data-ttu-id="a927f-127">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="a927f-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
