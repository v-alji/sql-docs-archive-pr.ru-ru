---
title: Выбор измерения исходного куба (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656601"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="febd0-102">Выбор измерения исходного куба (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="febd0-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="febd0-103">Используйте страницу **Выбор измерения исходного куба** для выбора измерения из куба, содержащего параметры, которые нужно проанализировать.</span><span class="sxs-lookup"><span data-stu-id="febd0-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="febd0-104">Например, если пользователь строит модель, которая анализирует поведение клиентов в процессе покупки на основе демографических данных, можно выбрать измерение «Клиент», которое обычно содержит уникальную запись для каждого клиента и различные атрибуты, представляющие демографические данные, например пол, место жительства или доход.</span><span class="sxs-lookup"><span data-stu-id="febd0-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="febd0-105">В ходе работы мастера можно будет добавить таблицу, связанную с данной таблицей вариантов, например: можно добавить вложенную таблицу, в которой будет показано, какие товары клиент уже купил.</span><span class="sxs-lookup"><span data-stu-id="febd0-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="febd0-106">Данная страница появляется только в случае выбора пункта **На основе существующего куба** на странице мастера **Выбор метода определения**.</span><span class="sxs-lookup"><span data-stu-id="febd0-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="febd0-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="febd0-107">Options</span></span>  
 <span data-ttu-id="febd0-108">**Выберите измерение исходного куба**</span><span class="sxs-lookup"><span data-stu-id="febd0-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="febd0-109">Выберите измерение куба, который будет предоставлять исходные данные для вашей структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="febd0-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="febd0-110">Выбор измерения</span><span class="sxs-lookup"><span data-stu-id="febd0-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="febd0-111">Поскольку для использования в модели можно выбрать только одно измерение, очень важно понимать структуру куба и выбрать измерение, в котором представлена оптимальная информация для данной модели.</span><span class="sxs-lookup"><span data-stu-id="febd0-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="febd0-112">Если нет уверенности в том, какое измерение следует использовать, просмотрите куб и найдите поля и данные с помощью конструктора измерений.</span><span class="sxs-lookup"><span data-stu-id="febd0-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="febd0-113">Дополнительные сведения см. в разделе [Просмотр данных измерения в конструкторе измерений](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="febd0-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="febd0-114">Если вы не знакомы с измерениями в целом, см. раздел [Введение в измерения (службы Analysis Services — многомерные данные)](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="febd0-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="febd0-115">Дополнительные сведения о типе информации, обычно содержащиеся в одном измерении (в том числе атрибутов и мер, которые могут пригодиться при интеллектуальном анализе данных), см. в разделе [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="febd0-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="febd0-116">Если выбранное измерение не содержит всех связанных атрибутов, необходимых для построения модели интеллектуального анализа данных, то это измерение, возможно, нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="febd0-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="febd0-117">Дополнительные сведения см. в разделе [Определение измерений базы данных](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="febd0-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febd0-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="febd0-118">See Also</span></span>  
 <span data-ttu-id="febd0-119">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="febd0-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="febd0-120">[Создание структуры интеллектуального анализа данных &#40;мастер интеллектуального анализа данных&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="febd0-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="febd0-121">Выберите ключ варианта &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="febd0-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
