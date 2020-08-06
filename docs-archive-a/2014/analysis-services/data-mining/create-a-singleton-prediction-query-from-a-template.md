---
title: Создание одноэлементного прогнозирующего запроса из шаблона | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656047"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="92409-102">создать одноэлементный прогнозирующий запрос из шаблона</span><span class="sxs-lookup"><span data-stu-id="92409-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="92409-103">Одноэлементный запрос полезен при наличии модели, которую нужно использовать для прогнозирования, но не нужно сопоставлять ее с внешним набором входных данных или выполнять групповые прогнозы.</span><span class="sxs-lookup"><span data-stu-id="92409-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="92409-104">Одноэлементный запрос позволяет предоставлять модели значения и мгновенно видеть спрогнозированное значение.</span><span class="sxs-lookup"><span data-stu-id="92409-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="92409-105">Например, следующий запрос расширений интеллектуального анализа данных представляет одноэлементный запрос к модели целевой рассылки, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="92409-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="92409-106">В следующей процедуре описано быстрое создание этого запроса с помощью обозревателя шаблонов в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92409-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="92409-107">Открытие образцов служб Analysis Services в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92409-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92409-108">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="92409-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="92409-109">Чтобы открыть шаблоны **сервера анализа данных**, щелкните значок куба.</span><span class="sxs-lookup"><span data-stu-id="92409-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="92409-110">Открытие шаблона прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="92409-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="92409-111">В **обозревателе шаблонов**в списке шаблонов сервера анализа данных разверните узел **Расширения интеллектуального анализа данных**, а затем узел **Запросы прогноза**.</span><span class="sxs-lookup"><span data-stu-id="92409-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="92409-112">Дважды щелкните **Одноэлементный прогноз**.</span><span class="sxs-lookup"><span data-stu-id="92409-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="92409-113">В диалоговом окне **Подключиться к службам Analysis Services** введите имя сервера, размещающего экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащий модель интеллектуального анализа данных, к которой будет обращен запрос.</span><span class="sxs-lookup"><span data-stu-id="92409-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="92409-114">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="92409-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="92409-115">Шаблон откроется в указанной базе данных вместе с обозревателем объектов модели интеллектуального анализа данных, содержащим функции интеллектуального анализа данных и список структур интеллектуального анализа данных и связанных с ними моделей.</span><span class="sxs-lookup"><span data-stu-id="92409-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="92409-116">Настройка шаблона одноэлементного запроса</span><span class="sxs-lookup"><span data-stu-id="92409-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="92409-117">В шаблоне щелкните раскрывающийся список **Доступные базы данных** и выберите из этого списка экземпляр служб Analysis Service.</span><span class="sxs-lookup"><span data-stu-id="92409-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="92409-118">В списке **Модель интеллектуального анализа данных** выберите модель, к которой будет адресован запрос.</span><span class="sxs-lookup"><span data-stu-id="92409-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="92409-119">На панели **Метаданные** обозревателя объектов появится список столбцов модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="92409-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="92409-120">В меню **Запрос** выберите пункт **Задание значений для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="92409-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="92409-121">В строке **список выбора** можно ввести символ "\*", чтобы возвращались все столбцы, либо список с разделителями-запятыми столбцов и выражений, чтобы возвращались определенные столбцы.</span><span class="sxs-lookup"><span data-stu-id="92409-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="92409-122">Если ввести символ «\*», то возвращается прогнозируемый столбец, а также все столбцы, для которых в шаге 6 были предоставлены новые значения.</span><span class="sxs-lookup"><span data-stu-id="92409-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="92409-123">В образце кода, приведенном в начале данного раздела, для строки **список выбора** было установлено значение "\*".</span><span class="sxs-lookup"><span data-stu-id="92409-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="92409-124">В строке **модель интеллектуального анализа данных** введите имя модели интеллектуального анализа данных, присутствующей в списке моделей, отображаемом в **Обозревателе объектов**.</span><span class="sxs-lookup"><span data-stu-id="92409-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="92409-125">Для примера кода, показанного в начале этого раздела, в строке **модели интеллектуального анализа данных** было задано имя, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="92409-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="92409-126">В строке **значение** введите новое значение данных, для которого необходимо создать прогноз.</span><span class="sxs-lookup"><span data-stu-id="92409-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="92409-127">В образце кода, приведенном в начале этого раздела, в строке **значение** было задано `2` прогнозирование поведения покупателя велосипеда в зависимости от числа детей дома.</span><span class="sxs-lookup"><span data-stu-id="92409-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="92409-128">В строке **столбец** введите имя столбца модели интеллектуального анализа данных, с которым должны быть сопоставлены новые данные.</span><span class="sxs-lookup"><span data-stu-id="92409-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="92409-129">Для примера кода, показанного в начале этого раздела, строке **столбца** было присвоено значение `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="92409-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92409-130">При работе с диалоговым окном **Задание значений для параметров шаблона** заключать имя столбца в квадратные скобки необязательно.</span><span class="sxs-lookup"><span data-stu-id="92409-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="92409-131">Они будут добавлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="92409-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="92409-132">Оставьте **входной псевдоним** как `t` .</span><span class="sxs-lookup"><span data-stu-id="92409-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="92409-133">На панели текста запроса найдите красное подчеркивание волнистой линией под запятой и многоточием, обозначающее синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="92409-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="92409-134">Удалите многоточие и добавьте любое дополнительное условие для запроса.</span><span class="sxs-lookup"><span data-stu-id="92409-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="92409-135">Если дополнительные условия добавляться не будут, удалите многоточие.</span><span class="sxs-lookup"><span data-stu-id="92409-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="92409-136">В образце кода, приведенном в начале данного раздела, вот что было задано в качестве дополнительного условия: `'45' as [Age]`.</span><span class="sxs-lookup"><span data-stu-id="92409-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="92409-137">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="92409-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92409-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="92409-138">See Also</span></span>  
 [<span data-ttu-id="92409-139">Создание прогнозов (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="92409-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
