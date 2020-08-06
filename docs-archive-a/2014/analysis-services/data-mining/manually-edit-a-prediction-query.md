---
title: Изменение прогнозирующего запроса вручную | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669172"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="f8eb5-102">Изменение прогнозирующего запроса вручную</span><span class="sxs-lookup"><span data-stu-id="f8eb5-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="f8eb5-103">После проектирования запроса с использованием построителя прогнозирующих запросов можно изменить этот запрос, переключившись в представление «Текст запроса» на вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="f8eb5-104">В нижней части экрана появится текстовый редактор, отображающий запрос, созданный построителем запросов.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="f8eb5-105">Переключение на представление «Текст запроса» полезно при внесении дополнений в запрос.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="f8eb5-106">Например, можно добавить предложение WHERE или ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="f8eb5-107">С помощью сетки в построителе прогнозирующих запросов можно вставить имена объектов и столбцов и настроить синтаксис отдельных прогнозирующих функций, а затем переключиться в режим ручного редактирования для изменения значений параметров.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8eb5-108">При переключении из представления **Текст запроса** обратно в представление **Проектирование** все изменения, внесенные в представлении **Текст запроса** , будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="f8eb5-109">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="f8eb5-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="f8eb5-110">На вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]нажмите кнопку **SQL**.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="f8eb5-111">Сетка в нижней части экрана заменится текстовым редактором, содержащим запрос.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="f8eb5-112">В этом редакторе можно ввести в запрос изменения.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="f8eb5-113">Чтобы запустить запрос, выберите в меню **Модель интеллектуального анализа данных** команду **Результат**или нажмите соответствующую кнопку для переключения на результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8eb5-114">Если созданный запрос содержит ошибку, в окне результатов не будут показаны результаты и не будет выведено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f8eb5-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="f8eb5-115">Чтобы исправить ошибку, нажмите кнопку **Конструктор** или выберите один из пунктов — **Конструктор** или **Запрос** — в меню **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="f8eb5-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8eb5-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8eb5-116">See Also</span></span>  
 <span data-ttu-id="f8eb5-117">[Запросы интеллектуального анализа данных](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="f8eb5-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="f8eb5-118">[Прогнозирование конструктор запросов &#40;интеллектуального анализа данных&#41;](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f8eb5-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="f8eb5-119">Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="f8eb5-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
