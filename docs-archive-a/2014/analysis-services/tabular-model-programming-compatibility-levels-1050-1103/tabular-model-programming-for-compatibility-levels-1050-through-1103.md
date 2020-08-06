---
title: Программирование табличных моделей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752376"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="286b3-102">Программирование табличных моделей</span><span class="sxs-lookup"><span data-stu-id="286b3-102">Tabular Model Programming</span></span>
  <span data-ttu-id="286b3-103">В табличных моделях реляционные конструкции служат для моделирования данных служб Analysis Services, которые используются в аналитических приложениях и отчетах.</span><span class="sxs-lookup"><span data-stu-id="286b3-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="286b3-104">Эти модели работают в экземпляре служб Analysis Services, настроенном для табличного режима, с использованием модуля аналитики в памяти для хранения и быстрого просмотра таблиц, при применении которого выполняется статистическая обработка и вычисление данных по запросу.</span><span class="sxs-lookup"><span data-stu-id="286b3-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="286b3-105">С программной точки зрения объекты, с которыми пользователь работает в объектах AMO, ADOMD.NET, XMLA и OLE DB, принципиально одинаковы для табличных и многомерных решений.</span><span class="sxs-lookup"><span data-stu-id="286b3-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="286b3-106">Если требованиям пользовательского решения для бизнес-аналитики лучше всего отвечает табличный шаблон базы данных, то для интеграции приложения с табличными моделями в экземпляре служб Analysis Services можно использовать любые клиентские библиотеки и интерфейсы программирования служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="286b3-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="286b3-107">Для запроса к данным табличной модели и вычисления таких данных можно использовать в коде внедренные многомерные выражения или DAX.</span><span class="sxs-lookup"><span data-stu-id="286b3-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="286b3-108">В этом разделе приведены дополнительные сведения о том, как программным образом работать с сущностями табличной модели и их свойствами.</span><span class="sxs-lookup"><span data-stu-id="286b3-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="286b3-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="286b3-109">In This Section</span></span>  
 [<span data-ttu-id="286b3-110">Заметки языка CSDL для бизнес-аналитики (CSDLBI)</span><span class="sxs-lookup"><span data-stu-id="286b3-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="286b3-111">Основные сведения о табличной объектной модели</span><span class="sxs-lookup"><span data-stu-id="286b3-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="286b3-112">Технический справочник по аннотациям бизнес-аналитики для языка CSDL</span><span class="sxs-lookup"><span data-stu-id="286b3-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="286b3-113">Интерфейс IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="286b3-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="286b3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="286b3-114">See Also</span></span>  
 <span data-ttu-id="286b3-115">[Табличное моделирование &#40;табличные&#41;SSAS](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="286b3-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="286b3-116">Конструктор табличных моделей &#40;табличные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="286b3-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
