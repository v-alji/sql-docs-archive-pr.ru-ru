---
title: Создать новую реляционную структуру интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656050"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="51f11-102">создать новую реляционную структуру интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51f11-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="51f11-103">Используйте мастер интеллектуального анализа данных, чтобы создать новую структуру интеллектуального анализа данных, используя данные из реляционной базы данных или другого источника, а затем сохраните структуру и все связанные модели в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="51f11-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="51f11-104">Создание реляционной структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51f11-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="51f11-105">В обозревателе решений щелкните правой кнопкой мыши папку **Структуры интеллектуального анализа данных** в проекте служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и выберите пункт **Создать структуру интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="51f11-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="51f11-106">Откроется мастер интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51f11-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="51f11-107">На странице **Вас приветствует мастер интеллектуального анализа данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="51f11-108">На странице **Выбор метода определения** выберите пункт **Из существующей реляционной базы данных или хранилища данных**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="51f11-109">На странице **Выбор технологии интеллектуального анализа данных** выберите необходимый алгоритм интеллектуального анализа данных и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="51f11-110">Дополнительные сведения об алгоритмах интеллектуального анализа данных см. в разделе [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="51f11-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="51f11-111">На странице **Выбор представления источников данных** в разделе **Доступные представления источников данных**выберите представление, которое необходимо использовать, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="51f11-112">Дополнительные сведения о создании и использовании источников данных и представлений источников данных см. в разделе [Представления источников данных в многомерных моделях](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="51f11-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="51f11-113">На странице **Задание типов таблицы** в разделе **Входные таблицы**выберите таблицу вариантов и вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="51f11-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="51f11-114">На странице **Задание обучающих данных** в разделе **Структура модели интеллектуального анализа данных**выберите ключевой, входной и прогнозируемый столбцы.</span><span class="sxs-lookup"><span data-stu-id="51f11-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="51f11-115">После выбора прогнозируемого столбца можно нажать кнопку **Варианты** , чтобы открыть диалоговое окно **Варианты связанных столбцов** .</span><span class="sxs-lookup"><span data-stu-id="51f11-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="51f11-116">Можно принять предлагаемые столбцы, нажав кнопку **ОК** в этом диалоговом окне, чтобы включить выбранные столбцы в структуру интеллектуального анализа данных, или сначала можно изменить выбор в столбце **Вход** , а затем нажать кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="51f11-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="51f11-117">Чтобы пропустить варианты, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="51f11-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="51f11-118">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="51f11-119">На странице **Задание содержимого и типа данных столбцов** в разделе **Структура интеллектуального анализа данных**можно указать тип содержимого и тип данных для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="51f11-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51f11-120">Чтобы автоматически определить содержание в столбце непрерывных или дискретных данных, можно нажать кнопку **Обнаружить** .</span><span class="sxs-lookup"><span data-stu-id="51f11-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="51f11-121">После нажатия этой кнопки типы содержимого и данных обновляются в столбцах **Тип содержимого** и **Тип данных** .</span><span class="sxs-lookup"><span data-stu-id="51f11-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="51f11-122">Дополнительные сведения о типах содержимого и типах данных см. в разделах [Типы содержимого (интеллектуальный анализ данных)](content-types-data-mining.md) и [Типы содержимого (интеллектуальный анализ данных)](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="51f11-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="51f11-123">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51f11-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="51f11-124">На странице **Завершение работы мастера** введите имя для структуры интеллектуального анализа и соответствующей первоначальной модели интеллектуального анализа данных, которая будет создана, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="51f11-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f11-125">См. также</span><span class="sxs-lookup"><span data-stu-id="51f11-125">See Also</span></span>  
 [<span data-ttu-id="51f11-126">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51f11-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
