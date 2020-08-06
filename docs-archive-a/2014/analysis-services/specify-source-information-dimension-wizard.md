---
title: Определение исходных сведений (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666767"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="8e3fa-102">Определение исходных сведений (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="8e3fa-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="8e3fa-103">Страница **Выбор основной таблицы измерения** позволяет выбрать представление источника данных, главную таблицу измерения, ключевые столбцы и столбец имен элементов для создаваемого измерения.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="8e3fa-104">**Открытие мастера измерений**</span><span class="sxs-lookup"><span data-stu-id="8e3fa-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="8e3fa-105">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]обозревателе решений \*\*\*\* щелкните правой кнопкой мыши папку **Измерения** для проекта [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а затем выберите команду **Новое измерение**.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e3fa-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="8e3fa-106">Options</span></span>  
 <span data-ttu-id="8e3fa-107">**Представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="8e3fa-107">**Data source view**</span></span>  
 <span data-ttu-id="8e3fa-108">Выберите представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="8e3fa-109">**Основная таблица**</span><span class="sxs-lookup"><span data-stu-id="8e3fa-109">**Main table**</span></span>  
 <span data-ttu-id="8e3fa-110">Выберите таблицу из выбранного представления источников данных в качестве главной таблицы для измерения.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="8e3fa-111">**Ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="8e3fa-111">**Key columns**</span></span>  
 <span data-ttu-id="8e3fa-112">Выберите ключевые столбцы из таблицы, указанной в поле **Основная таблица** , для ключевого атрибута данного измерения.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e3fa-113">Можно выбрать несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-113">More than one column can be selected.</span></span> <span data-ttu-id="8e3fa-114">Если таблица содержит составной первичный ключ, выберите все столбцы, входящие в этот ключ.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="8e3fa-115">Важен порядок ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="8e3fa-116">**Столбец имени**</span><span class="sxs-lookup"><span data-stu-id="8e3fa-116">**Name column**</span></span>  
 <span data-ttu-id="8e3fa-117">Выберите столбец, содержащий имена членов для данного измерения, из таблицы, указанной в поле **Основная таблица** .</span><span class="sxs-lookup"><span data-stu-id="8e3fa-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="8e3fa-118">Необходимо указать столбец имени, прежде чем составной ключ будет доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="8e3fa-119">Чтобы создать столбец имени для составного ключа, рекомендуется создать именованное вычисление в представлении источника данных, объединяющем указанные ключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="8e3fa-120">Если используется единственный ключ, то столбец имени необязателен.</span><span class="sxs-lookup"><span data-stu-id="8e3fa-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3fa-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e3fa-121">See Also</span></span>  
 <span data-ttu-id="8e3fa-122">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8e3fa-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="8e3fa-123">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8e3fa-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8e3fa-124">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="8e3fa-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
