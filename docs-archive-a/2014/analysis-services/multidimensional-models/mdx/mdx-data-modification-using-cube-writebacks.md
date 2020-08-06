---
title: Обратная запись в куб (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658449"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="70e87-102">Обратная запись в куб (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="70e87-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="70e87-103">Для обновления куба используется инструкция [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="70e87-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="70e87-104">Эта инструкция позволяет записать в кортеж указанное значение.</span><span class="sxs-lookup"><span data-stu-id="70e87-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="70e87-105">Для эффективного использования инструкции UPDATE CUBE необходимо понимать ее синтаксис, ситуации, в которых может возникнуть ошибка, и влияние обновления на весь куб.</span><span class="sxs-lookup"><span data-stu-id="70e87-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="70e87-106">Синтаксис инструкции UPDATE CUBE</span><span class="sxs-lookup"><span data-stu-id="70e87-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="70e87-107">Синтаксис инструкции UPDATE CUBE приведен далее.</span><span class="sxs-lookup"><span data-stu-id="70e87-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="70e87-108">Если для кортежа не указан полный набор координат, вместо неуказанных координат используется элемент иерархии по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70e87-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="70e87-109">Заданный кортеж должен ссылаться на ячейку, которая содержит статистическое значение, полученное с помощью функции [Sum](/sql/mdx/sum-mdx) . В качестве координат ячейки нельзя использовать вычисляемые элементы.</span><span class="sxs-lookup"><span data-stu-id="70e87-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="70e87-110">Инструкция UPDATE CUBE подобна подпрограмме, выполняющей серию отдельных операций обратной записи в элементарные ячейки.</span><span class="sxs-lookup"><span data-stu-id="70e87-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="70e87-111">Затем отдельные операции обратной записи сводятся в указанную сумму.</span><span class="sxs-lookup"><span data-stu-id="70e87-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70e87-112">Если обновленные ячейки не пересекаются, свойство строки подключения `Update Isolation Level` может быть использовано для повышения производительности инструкции UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="70e87-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="70e87-113">Дополнительные сведения см. в разделе <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="70e87-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e87-114">Пример</span><span class="sxs-lookup"><span data-stu-id="70e87-114">Example</span></span>  
 <span data-ttu-id="70e87-115">Можно проверить инструкцию UPDATE CUBE с помощью группы мер Sales Targets в кубе Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="70e87-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="70e87-116">Эта группа мер состоит из мер, суммированных с помощью функции SUM, которая обязательна для UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="70e87-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="70e87-117">Разрешение обратной записи для группы мер Sales Targets в базе данных Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="70e87-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="70e87-118">В среде Management Studio щелкните группу мер правой кнопкой мыши, наведите указатель мыши на пункт **Параметры запуска**и выберите пункт **Включить обратную запись**.</span><span class="sxs-lookup"><span data-stu-id="70e87-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="70e87-119">Появится новая таблица обратных записей в папке обратных записей.</span><span class="sxs-lookup"><span data-stu-id="70e87-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="70e87-120">Имя таблицы — WriteTable_Fact Sales Quota.</span><span class="sxs-lookup"><span data-stu-id="70e87-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="70e87-121">Откройте окно запроса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="70e87-121">Open an MDX query window.</span></span> <span data-ttu-id="70e87-122">Чтобы просмотреть исходное значение, выполните следующую инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="70e87-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="70e87-123">Появятся квоты продаж по каждому представителю.</span><span class="sxs-lookup"><span data-stu-id="70e87-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="70e87-124">Выполните инструкцию обновления куба, чтобы записать новое значение.</span><span class="sxs-lookup"><span data-stu-id="70e87-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="70e87-125">В этом примере рекомендуется задать значение 0 для квоты продаж.</span><span class="sxs-lookup"><span data-stu-id="70e87-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="70e87-126">Поскольку новое значение равно 0, не указывайте способ распределения.</span><span class="sxs-lookup"><span data-stu-id="70e87-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="70e87-127">Выполните инструкцию SELECT еще раз.</span><span class="sxs-lookup"><span data-stu-id="70e87-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="70e87-128">Значение для квот теперь будет равно 0.</span><span class="sxs-lookup"><span data-stu-id="70e87-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="70e87-129">Значение обратной записи ограничивается текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="70e87-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="70e87-130">Чтобы сохранить значение для других пользователей и сеансов, выполните обработку таблицы обратных записей.</span><span class="sxs-lookup"><span data-stu-id="70e87-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="70e87-131">В среде Management Studio щелкните правой кнопкой мыши WriteTable_Fact Sales Quota и выберите **Обработка**.</span><span class="sxs-lookup"><span data-stu-id="70e87-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="70e87-132">Чтобы указать способ распределения, нужно задать новое значение больше нуля.</span><span class="sxs-lookup"><span data-stu-id="70e87-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="70e87-133">В этом примере новое значение для квоты продаж равно двум миллионам, а способ распределения распределяет сумму по всем торговым представителям.</span><span class="sxs-lookup"><span data-stu-id="70e87-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="70e87-134">Ситуации, которые могут привести к ошибке</span><span class="sxs-lookup"><span data-stu-id="70e87-134">Error Conditions</span></span>  
 <span data-ttu-id="70e87-135">В следующей таблице описаны причины возможных ошибок обратной записи и их результаты.</span><span class="sxs-lookup"><span data-stu-id="70e87-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="70e87-136">Условие возникновения ошибки</span><span class="sxs-lookup"><span data-stu-id="70e87-136">Error Condition</span></span>|<span data-ttu-id="70e87-137">Результат</span><span class="sxs-lookup"><span data-stu-id="70e87-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="70e87-138">Инструкция обновления содержит элементы одного и того же измерения, которые не существуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="70e87-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="70e87-139">Обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="70e87-139">Update will fail.</span></span> <span data-ttu-id="70e87-140">Пространство куба не будет содержать ячейку, на которую ссылается инструкция.</span><span class="sxs-lookup"><span data-stu-id="70e87-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="70e87-141">Инструкция обновления содержит меру, источником которой является мера беззнакового типа данных.</span><span class="sxs-lookup"><span data-stu-id="70e87-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="70e87-142">Обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="70e87-142">Update will fail.</span></span> <span data-ttu-id="70e87-143">При приращении необходимо, чтобы мера могла принимать отрицательные значения.</span><span class="sxs-lookup"><span data-stu-id="70e87-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="70e87-144">Инструкция обновления содержит меру, которая соответствует не сумме, а другому статистическому выражению.</span><span class="sxs-lookup"><span data-stu-id="70e87-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="70e87-145">Возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="70e87-145">An error is raised.</span></span>|  
|<span data-ttu-id="70e87-146">Попытка обновления вложенного куба.</span><span class="sxs-lookup"><span data-stu-id="70e87-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="70e87-147">Возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="70e87-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="70e87-148">Зависимость от изменений куба</span><span class="sxs-lookup"><span data-stu-id="70e87-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="70e87-149">Следующие изменения не влияют на обратную запись.</span><span class="sxs-lookup"><span data-stu-id="70e87-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="70e87-150">Обработка куба, групп его мер или измерений.</span><span class="sxs-lookup"><span data-stu-id="70e87-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="70e87-151">Добавление атрибутов в любое измерение.</span><span class="sxs-lookup"><span data-stu-id="70e87-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="70e87-152">Добавление нового измерения.</span><span class="sxs-lookup"><span data-stu-id="70e87-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="70e87-153">Удаление измерения, которое не содержит обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="70e87-154">Добавление, изменение и удаление иерархии.</span><span class="sxs-lookup"><span data-stu-id="70e87-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="70e87-155">Добавление новой меры.</span><span class="sxs-lookup"><span data-stu-id="70e87-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="70e87-156">Следующие изменения нельзя выполнить без удаления данных обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="70e87-157">Удаление атрибута или его иерархии, если атрибут содержится в обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="70e87-158">Под этим подразумевается явное удаление атрибута или его иерархии, либо удаление родительского измерения атрибута.</span><span class="sxs-lookup"><span data-stu-id="70e87-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="70e87-159">Удаление меры, которая содержится в обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="70e87-160">Добавление атрибута без уровня `(All)` в измерение, которое содержится в обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="70e87-161">Изменение степени гранулярности измерения, которое содержится в обратной записи.</span><span class="sxs-lookup"><span data-stu-id="70e87-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e87-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="70e87-162">See Also</span></span>  
 [<span data-ttu-id="70e87-163">Изменение данных (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="70e87-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
