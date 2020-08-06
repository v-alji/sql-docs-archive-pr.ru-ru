---
title: Занятие 3. Обработка структуры интеллектуального анализа данных покупателя велосипеда | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734694"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="2df82-102">Урок 3. Обработка структуры интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="2df82-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="2df82-103">На этом занятии для обработки структур и моделей интеллектуального анализа данных, созданных на занятии 1, вы будете использовать инструкцию INSERT INTO и представление vTargetMail из примера. для этого нужно создать [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] [структуру интеллектуального анализа данных для покупателя велосипеда](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) и [занятие 2](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="2df82-104">При обработке структуры интеллектуального анализа данных службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] считывают исходные данные и создают структуры, поддерживающие модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="2df82-105">При обработке модели интеллектуального анализа данных данные, определенные структурой интеллектуального анализа данных, проходят через выбранный пользователем алгоритм интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="2df82-106">Алгоритм находит тренды и шаблоны и сохраняет эти данные в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="2df82-107">Поэтому в модели интеллектуального анализа данных содержатся не фактические исходные данные, а данные, выявленные алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="2df82-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="2df82-108">Дополнительные сведения об обработке моделей интеллектуального анализа данных см. в разделе [требования к обработке и рекомендации &#40;&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="2df82-109">Повторная обработка структуры интеллектуального анализа данных нужна только в том случае, когда изменяются столбцы структуры или исходные данные.</span><span class="sxs-lookup"><span data-stu-id="2df82-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="2df82-110">При добавлении модели интеллектуального анализа данных к уже обработанной структуре интеллектуального анализа данных можно использовать инструкцию INSERT INTO MINING MODEL для обучения новой модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="2df82-111">Шаблон обучения структуры</span><span class="sxs-lookup"><span data-stu-id="2df82-111">Train Structure Template</span></span>  
 <span data-ttu-id="2df82-112">Чтобы обучить структуру интеллектуального анализа данных и связанные с ней модели интеллектуального анализа данных, используйте инструкцию [INSERT в &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="2df82-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="2df82-113">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="2df82-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="2df82-114">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="2df82-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="2df82-115">Список столбцов структуры интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="2df82-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="2df82-116">Определение обучающих данных</span><span class="sxs-lookup"><span data-stu-id="2df82-116">Defining the training data</span></span>  
  
 <span data-ttu-id="2df82-117">В следующем фрагменте показан общий пример инструкции INSERT INTO:</span><span class="sxs-lookup"><span data-stu-id="2df82-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="2df82-118">В первой строчке кода задается структура интеллектуального анализа данных, которую необходимо обучить:</span><span class="sxs-lookup"><span data-stu-id="2df82-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="2df82-119">Следующая строка кода указывает столбцы, определенные структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="2df82-120">Необходимо перечислить все столбцы структуры интеллектуального анализа данных, и каждый столбец должен сопоставляться с каким-либо столбцом из данных исходного запроса.</span><span class="sxs-lookup"><span data-stu-id="2df82-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="2df82-121">Последней строчкой кода определяются данные, с помощью которых будет проводиться обучение структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="2df82-122">На этом занятии требуется определить исходные данные с помощью инструкции `OPENQUERY`.</span><span class="sxs-lookup"><span data-stu-id="2df82-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="2df82-123">Дополнительные сведения о других методах определения исходного запроса см. в разделе [&#60;Source Data query&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="2df82-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="2df82-124">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="2df82-124">Lesson Tasks</span></span>  
 <span data-ttu-id="2df82-125">На этом занятии требуется выполнить следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="2df82-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="2df82-126">Обработка структуры интеллектуального анализа данных «Покупатель велосипеда»</span><span class="sxs-lookup"><span data-stu-id="2df82-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="2df82-127">Обработка прогнозирующей структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="2df82-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="2df82-128">Обработка структуры интеллектуального анализа данных с помощью инструкции INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="2df82-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="2df82-129">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="2df82-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="2df82-130">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="2df82-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="2df82-131">Скопируйте стандартный пример использования инструкции INSERT INTO в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="2df82-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="2df82-132">Вместо</span><span class="sxs-lookup"><span data-stu-id="2df82-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="2df82-133">на:</span><span class="sxs-lookup"><span data-stu-id="2df82-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="2df82-134">Вместо</span><span class="sxs-lookup"><span data-stu-id="2df82-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="2df82-135">на:</span><span class="sxs-lookup"><span data-stu-id="2df82-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
    [Commute Distance],  
    [Education],  
    [Gender],  
    [House Owner Flag],  
    [Marital Status],  
    [Number Cars Owned],  
    [Number Children At Home],  
    [Occupation],  
    [Region],  
    [Total Children],  
    [Yearly Income]  
    ```  
  
5.  <span data-ttu-id="2df82-136">Вместо</span><span class="sxs-lookup"><span data-stu-id="2df82-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="2df82-137">на:</span><span class="sxs-lookup"><span data-stu-id="2df82-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="2df82-138">В инструкции OPENQUERY для доступа к представлению vTargetMail указан источник данных [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2df82-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="2df82-139">В указанном представлении содержатся исходные данные, которые будут использоваться для обучения моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2df82-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="2df82-140">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2df82-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]     
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="2df82-141">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="2df82-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="2df82-142">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="2df82-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="2df82-143">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="2df82-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="2df82-144">На следующем занятии будет изучено содержимое моделей интеллектуального анализа данных, добавленных к структуре интеллектуального анализа данных на текущем занятии.</span><span class="sxs-lookup"><span data-stu-id="2df82-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2df82-145">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="2df82-145">Next Lesson</span></span>  
 [<span data-ttu-id="2df82-146">Занятие 4: Просмотр моделей интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="2df82-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
