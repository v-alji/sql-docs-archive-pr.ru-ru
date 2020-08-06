---
title: Отображение скрытых наборов данных для значений параметров в многомерных данные (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb01c4ca-4fd6-4629-b595-f0d2565915df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9c005b6e7c8927316c19a3302e32f4407f9885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751752"
---
# <a name="show-hidden-datasets-for-parameter-values-for-multidimensional-data-report-builder-and-ssrs"></a><span data-ttu-id="9a37f-102">Отображение скрытых наборов данных для значений параметра в многомерных данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9a37f-102">Show Hidden Datasets for Parameter Values for Multidimensional Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9a37f-103">Отчет может включать автоматически создаваемые наборы данных (называемые также скрытыми наборами данных), которые по умолчанию не отображаются на панели данных отчета.</span><span class="sxs-lookup"><span data-stu-id="9a37f-103">Your report might include automatically-generated datasets (also known as hidden datasets) that do not appear by default in the Report Data pane.</span></span> <span data-ttu-id="9a37f-104">Эти наборы данных создаются следующими способами.</span><span class="sxs-lookup"><span data-stu-id="9a37f-104">These datasets are created in the following ways:</span></span>  
  
-   <span data-ttu-id="9a37f-105">В некоторых конструкторах запросов для многомерных баз данных можно указать поля для фильтрации в области фильтра панели запроса, и выбрать, создавать ли параметр запроса для фильтра.</span><span class="sxs-lookup"><span data-stu-id="9a37f-105">In some query designers for multidimensional databases, you can specify fields to filter on in the filter area of the query pane, and select whether to create a query parameter for the filter.</span></span> <span data-ttu-id="9a37f-106">Если выбран режим параметров, наборы данных отчета создаются автоматически, чтобы предоставлять допустимые значения для параметра отчета.</span><span class="sxs-lookup"><span data-stu-id="9a37f-106">If you select the parameter option, report datasets are automatically created to provide valid values for the report parameter.</span></span>  
  
-   <span data-ttu-id="9a37f-107">При импортировании запроса, основанного на многомерных базах данных, в отчет можно также включить скрытые наборы данных.</span><span class="sxs-lookup"><span data-stu-id="9a37f-107">If you import a query based on multidimensional databases, you might also include hidden datasets in your report.</span></span>  
  
 <span data-ttu-id="9a37f-108">Скрытые наборы данных недоступны для использования из мастера.</span><span class="sxs-lookup"><span data-stu-id="9a37f-108">Hidden datasets are not available to use from a wizard.</span></span>  
  
 <span data-ttu-id="9a37f-109">Можно сменить представление в области данных отчета, чтобы отображать в отчете все наборы данных.</span><span class="sxs-lookup"><span data-stu-id="9a37f-109">You can change the view in the Report Data pane to display all datasets in the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-hidden-datasets"></a><span data-ttu-id="9a37f-110">Отображение скрытых наборов данных</span><span class="sxs-lookup"><span data-stu-id="9a37f-110">To display hidden datasets</span></span>  
  
-   <span data-ttu-id="9a37f-111">В области данных отчета щелкните правой кнопкой мыши "Наборы данных" и выберите **Показать скрытые наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="9a37f-111">In the Report Data pane, right-click the Datasets folder, and then click **Show Hidden Datasets**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a37f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a37f-112">See Also</span></span>  
 <span data-ttu-id="9a37f-113">[Конструкторы запросов &#40;построитель отчетов&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="9a37f-113">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="9a37f-114">[Конструкторы запросов служб Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="9a37f-114">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 <span data-ttu-id="9a37f-115">[Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9a37f-115">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9a37f-116">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9a37f-116">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
  
  
