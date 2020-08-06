---
title: Импорт из многомерного источника данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668493"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="09eb8-102">Импорт из многомерного источника данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="09eb8-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="09eb8-103">В качестве источника данных для табличной модели можно использовать базу данных куба служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="09eb8-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="09eb8-104">Чтобы импортировать данные из куба служб Analysis Services, необходимо указать запрос многомерных выражений для выбора данных.</span><span class="sxs-lookup"><span data-stu-id="09eb8-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="09eb8-105">Любые данные, которые содержатся в базе данных служб SQL Server Analysis Services, можно импортировать в модель.</span><span class="sxs-lookup"><span data-stu-id="09eb8-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="09eb8-106">Можно извлечь все измерения или их часть, получить срезы и статистические выражения из куба, например суммы продаж по месяцам за текущий год и т. д. Однако необходимо иметь в виду, что все данные, импортируемые из куба, имеют плоский формат.</span><span class="sxs-lookup"><span data-stu-id="09eb8-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="09eb8-107">Поэтому, если определить запрос, который получает меры с несколькими измерениями, данные будут импортированы для каждого измерения в отдельном столбце.</span><span class="sxs-lookup"><span data-stu-id="09eb8-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="09eb8-108">Кубы служб Analysis Services должны иметь версию SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]или [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09eb8-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="09eb8-109">Импортировать данные из куба служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="09eb8-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="09eb8-110">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="09eb8-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="09eb8-111">На странице **Соединение с источником данных** выберите службы **Microsoft Analysis Services**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09eb8-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="09eb8-112">Выполните шаги мастера импорта таблиц.</span><span class="sxs-lookup"><span data-stu-id="09eb8-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="09eb8-113">На странице **Указание запроса MDX** можно указать запрос многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="09eb8-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="09eb8-114">Для использования конструктора запросов многомерных выражений нажмите кнопку **Конструирование**на странице «Указание запроса MDX».</span><span class="sxs-lookup"><span data-stu-id="09eb8-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09eb8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="09eb8-115">See Also</span></span>  
 <span data-ttu-id="09eb8-116">[Импорт данных &#40;табличные&#41;SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="09eb8-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="09eb8-117">Поддерживаемые источники данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="09eb8-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
