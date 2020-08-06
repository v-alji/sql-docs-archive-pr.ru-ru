---
title: Создание связанной модели кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734734"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="df7e4-102">Построение связанной модели кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="df7e4-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="df7e4-103">В результате исследования модели кластеризации последовательностей выяснилось, что другие атрибуты, например, Region или Income, оказывают значительное влияние на модели. Поэтому, чтобы упростить понимание последовательностей, будет создана связанная модель кластеризации последовательностей и будут удалены атрибуты, относящиеся к демографическим данным клиента.</span><span class="sxs-lookup"><span data-stu-id="df7e4-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="df7e4-104">В этой задаче будет создана копия региональной модели кластеризации последовательностей, затем из модели будут удалены все столбцы, непосредственно не связанные с последовательностями.</span><span class="sxs-lookup"><span data-stu-id="df7e4-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="df7e4-105">Новая модель будет содержать те же столбцы, что и модель интеллектуального анализа данных, на основе которой она создана.</span><span class="sxs-lookup"><span data-stu-id="df7e4-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="df7e4-106">Однако из структуры интеллектуального анализа данных не нужно удалять столбцы, необходимо только указать, что новая модель интеллектуального анализа данных не учитывает столбцы.</span><span class="sxs-lookup"><span data-stu-id="df7e4-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="df7e4-107">Создание копии модели кластеризации последовательностей</span><span class="sxs-lookup"><span data-stu-id="df7e4-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="df7e4-108">В в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] конструкторе интеллектуального анализа данных перейдите на вкладку **модели интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="df7e4-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="df7e4-109">Щелкните правой кнопкой мыши модель, которую необходимо скопировать, и выберите пункт **создать модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="df7e4-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="df7e4-110">В диалоговом окне **Новая модель интеллектуального анализа данных** введите имя модели и выберите Microsoft `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="df7e4-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="df7e4-111">В этом руководстве введите имя `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="df7e4-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="df7e4-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="df7e4-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="df7e4-113">Удаление столбцов из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="df7e4-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="df7e4-114">На вкладке **модель интеллектуального анализа данных** в столбце для новой модели с именем Кластеризация последовательностей щелкните строку для атрибута **Группа доходов** и выберите **пропустить**.</span><span class="sxs-lookup"><span data-stu-id="df7e4-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="df7e4-115">Повторите этот шаг для **области**атрибута.</span><span class="sxs-lookup"><span data-stu-id="df7e4-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="df7e4-116">Щелкните знак «плюс» рядом с именем таблицы **v Assoc Seq Line Items**, чтобы развернуть таблицу и просмотреть столбцы из вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="df7e4-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="df7e4-117">Новая модель должна иметь только следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="df7e4-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="df7e4-118">**Упорядочить Нумберкэй**</span><span class="sxs-lookup"><span data-stu-id="df7e4-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="df7e4-119">**Ключ номера строки**</span><span class="sxs-lookup"><span data-stu-id="df7e4-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="df7e4-120">**Прогноз модели**</span><span class="sxs-lookup"><span data-stu-id="df7e4-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="df7e4-121">Обработка новой модели кластеризации последовательностей</span><span class="sxs-lookup"><span data-stu-id="df7e4-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="df7e4-122">На вкладке **модель интеллектуального анализа данных** щелкните правой кнопкой мыши новую модель с именем `Sequence Clustering` и выберите команду **обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="df7e4-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="df7e4-123">Новая упрощенная модель интеллектуального анализа данных основана на структуре, которая уже обработана, поэтому повторная обработка структуры не требуется.</span><span class="sxs-lookup"><span data-stu-id="df7e4-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="df7e4-124">Можно обработать только новую модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="df7e4-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="df7e4-125">Нажмите кнопку **Да** , чтобы развернуть обновленный проект интеллектуального анализа данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="df7e4-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="df7e4-126">В диалоговом окне **Обработка модели интеллектуального анализа данных** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="df7e4-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="df7e4-127">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Ход обработки** , а затем еще раз нажмите кнопку **Закрыть** в диалоговом окне **Обработка модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="df7e4-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="df7e4-128">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="df7e4-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="df7e4-129">Создание прогнозов на модели кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="df7e4-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="df7e4-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="df7e4-130">See Also</span></span>  
 [<span data-ttu-id="df7e4-131">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="df7e4-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
