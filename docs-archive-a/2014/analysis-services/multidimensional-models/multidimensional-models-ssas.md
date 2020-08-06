---
title: Многомерное моделирование (службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752468"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="f7f9b-102">Многомерное моделирование (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="f7f9b-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="f7f9b-103">Многомерное решение служб Analysis Services использует структуры кубов для анализа бизнес-данных по нескольким измерениям.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="f7f9b-104">Многомерный режим является режимом сервера по умолчанию для служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="f7f9b-105">Он включает подсистему запросов и вычислений для данных OLAP с режимами хранения HOLAP, MOLAP и ROLAP, сочетающий производительность с требованиями к масштабируемости данных.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="f7f9b-106">Ядро OLAP служб Analysis Services является лучшим в отрасли сервером OLAP, хорошо работающим с широким диапазоном средств бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="f7f9b-107">В большинстве случаев службы Analysis Services устанавливаются как обычные серверы OLAP.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="f7f9b-108">Преимущества использования многомерных решений</span><span class="sxs-lookup"><span data-stu-id="f7f9b-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="f7f9b-109">Основной причиной для построения многомерной модели службы Analysis Services является достижение высокой производительности нерегламентированных запросов к бизнес-данным.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="f7f9b-110">Многомерная модель состоит из кубов и измерений, которые могут быть аннотированы и расширены для поддержки сложных конструкций запросов.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="f7f9b-111">Разработчики бизнес-аналитики создают кубы для поддержки малого времени ответа, а также для предоставления единого источника данных для бизнес-отчетности.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="f7f9b-112">При растущей важности бизнес-аналитики на всех уровнях организации единый источник аналитических данных обеспечивает минимизацию разногласий, если не полное их устранение.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="f7f9b-113">Другим важным преимуществом использования многомерных баз данных служб Analysis Services является интеграция с распространенными средствами создания отчетов бизнес-аналитики, например Excel, службами Reporting Services и PerformancePoint, а также с пользовательскими приложениями и решениям сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="f7f9b-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7f9b-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f7f9b-114">In This Section</span></span>  
 [<span data-ttu-id="f7f9b-115">Решения многомерной модели (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="f7f9b-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="f7f9b-116">Базы данных многомерных моделей (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="f7f9b-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="f7f9b-117">Обработка объектов многомерной модели</span><span class="sxs-lookup"><span data-stu-id="f7f9b-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="f7f9b-118">Роли и разрешения (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f7f9b-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="f7f9b-119">Power View для многомерных моделей</span><span class="sxs-lookup"><span data-stu-id="f7f9b-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="f7f9b-120">Управление сборками многомерной модели</span><span class="sxs-lookup"><span data-stu-id="f7f9b-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
