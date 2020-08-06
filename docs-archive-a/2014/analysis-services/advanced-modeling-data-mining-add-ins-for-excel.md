---
title: Расширенное моделирование (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656951"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="a4c45-102">Расширенное моделирование (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="a4c45-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="a4c45-103">С помощью **расширенных** параметров моделирования данных можно создавать пользовательские структуры и модели интеллектуального анализа данных, параметры которых отличаются от параметров, созданных мастерами.</span><span class="sxs-lookup"><span data-stu-id="a4c45-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="a4c45-104">Два мастера, описание которых содержится в этом разделе, помогут создать полностью новые структуры интеллектуального анализа данных или добавить модели интеллектуального анализа данных к уже существующим структурам интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a4c45-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="a4c45-105">Создание структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="a4c45-105">Create Mining Structure</span></span>  
 <span data-ttu-id="a4c45-106">![Кнопка «Создать структуру интеллектуального анализа данных» на ленте «Интеллектуальный анализ данных»](media/dmc-createstruct.gif "Кнопка «Создать структуру интеллектуального анализа данных» на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="a4c45-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="a4c45-107">**Мастер создания структуры интеллектуального анализа** данных помогает создать новую структуру интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="a4c45-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="a4c45-108">Структура — это набор данных, извлеченный из указанного источника данных.</span><span class="sxs-lookup"><span data-stu-id="a4c45-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="a4c45-109">Структуру интеллектуального анализа данных можно обновить новыми данными в источнике, но при создании структуры определяются имена и типы данных, которые определяют, каким образом данные используются для анализа.</span><span class="sxs-lookup"><span data-stu-id="a4c45-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="a4c45-110">Для построения структуры можно использовать следующие источники данных: таблицу Excel, диапазон Excel или любые данные во внешнем источнике данных, которые уже определены как [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="a4c45-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="a4c45-111">Для каждой структуры существует возможность зарезервировать определенное количество данных, которые будут использоваться при испытаниях и проверках.</span><span class="sxs-lookup"><span data-stu-id="a4c45-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="a4c45-112">Создавая этот *набор контрольных данных* при настройке источников данных, можно убедиться, что все модели, основанные на структуре, могут использовать последовательный набор данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="a4c45-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="a4c45-113">После создания структуры интеллектуального анализа данных можно добавить несколько моделей для применения различных методов анализа.</span><span class="sxs-lookup"><span data-stu-id="a4c45-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="a4c45-114">Дополнительные сведения об использовании **мастера создания структуры интеллектуального анализа**данных см. в статьях [Создание структуры интеллектуального анализа &#40;SQL Server надстройки интеллектуального анализа&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a4c45-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="a4c45-115">Добавление модели в структуру</span><span class="sxs-lookup"><span data-stu-id="a4c45-115">Add Model to Structure</span></span>  
 <span data-ttu-id="a4c45-116">![Кнопка «Добавить модель к структуре»](media/dmc-addmodel.gif "Кнопка «Добавить модель к структуре»")</span><span class="sxs-lookup"><span data-stu-id="a4c45-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="a4c45-117">При добавлении новой модели в структуру происходит анализ данных с помощью различных алгоритмов или параметров.</span><span class="sxs-lookup"><span data-stu-id="a4c45-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="a4c45-118">Этот параметр особенно полезен, если нужно создать модель с помощью одного из алгоритмов, не предоставляемых в клиентских средствах интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a4c45-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="a4c45-119">Например, можно использовать любой из алгоритмов, поддерживаемых службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4c45-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="a4c45-120">Линейная регрессия</span><span class="sxs-lookup"><span data-stu-id="a4c45-120">Linear regression</span></span>  
  
-   <span data-ttu-id="a4c45-121">Кластеризация последовательностей</span><span class="sxs-lookup"><span data-stu-id="a4c45-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="a4c45-122">Анализ взаимосвязей для вложенных наборов данных</span><span class="sxs-lookup"><span data-stu-id="a4c45-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="a4c45-123">Чтобы узнать, какие структуры интеллектуального анализа данных доступны, можно просмотреть модели и структуры, сохраненные в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , щелкнув **Управление моделями** или **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="a4c45-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="a4c45-124">Отображаются структуры интеллектуального анализа данных, которые были созданы в течение текущего сеанса, или структуры интеллектуального анализа данных, сохраненных в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4c45-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a4c45-125">Дополнительные сведения см. в разделе [Добавление модели в структуру &#40;надстройки интеллектуального анализа данных для&#41;Excel ](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a4c45-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c45-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4c45-126">See Also</span></span>  
 <span data-ttu-id="a4c45-127">[Управление моделями &#40;SQL Server надстроек интеллектуального анализа данных&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="a4c45-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="a4c45-128">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="a4c45-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
