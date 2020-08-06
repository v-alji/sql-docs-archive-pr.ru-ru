---
title: Изменение источника секции для использования другой таблицы фактов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737154"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="ed78c-102">Смена источника секции на другую таблицу фактов</span><span class="sxs-lookup"><span data-stu-id="ed78c-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="ed78c-103">При создании секции для куба можно использовать различные таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="ed78c-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="ed78c-104">Таблицы могут принадлежать представлению отдельного источника данных, представлениям различных источников данных или различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="ed78c-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="ed78c-105">Представление источника данных также может содержать различные таблицы из нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="ed78c-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="ed78c-106">Все таблицы фактов и измерения для секций куба должны иметь такую же структуру, как таблица фактов и измерения куба.</span><span class="sxs-lookup"><span data-stu-id="ed78c-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="ed78c-107">Например, различные таблицы фактов могут иметь одинаковую структуру, но содержать данные за разные годы или для разных линий продукции.</span><span class="sxs-lookup"><span data-stu-id="ed78c-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="ed78c-108">Укажите таблицу фактов на странице **Определение исходных сведений** мастера секционирования.</span><span class="sxs-lookup"><span data-stu-id="ed78c-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="ed78c-109">На этой странице в группе «Источник секции» в списке **Поиск в**укажите источник данных или представление источника данных, в котором требуется выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="ed78c-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="ed78c-110">Затем нажмите кнопку **Найти таблицы**и в разделе **Доступные таблицы**выберите нужные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ed78c-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="ed78c-111">Если используются различные таблицы фактов, то убедитесь, что данные в секциях не дублируются.</span><span class="sxs-lookup"><span data-stu-id="ed78c-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="ed78c-112">Например, если одна таблица фактов содержит транзакции только за 2012 год и другая — за 2013, то эти таблицы содержат независимые данные.</span><span class="sxs-lookup"><span data-stu-id="ed78c-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="ed78c-113">Таблицы фактов для отдельных линий продукции или отдельных географических областей также являются независимыми.</span><span class="sxs-lookup"><span data-stu-id="ed78c-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="ed78c-114">Можно, но не рекомендуется, использовать различные таблицы фактов с дублирующимися данными.</span><span class="sxs-lookup"><span data-stu-id="ed78c-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="ed78c-115">В этом случае необходимо использовать фильтры в секциях, чтобы гарантировать, что данные, используемые одной секцией, не используются другой.</span><span class="sxs-lookup"><span data-stu-id="ed78c-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="ed78c-116">Дополнительные сведения см. в разделе [Создание локальной секции и управление ею (службы Analysis Services)](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ed78c-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed78c-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed78c-117">See Also</span></span>  
 [<span data-ttu-id="ed78c-118">Создание локальной секции и управление ею (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ed78c-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
