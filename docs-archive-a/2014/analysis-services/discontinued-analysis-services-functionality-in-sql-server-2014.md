---
title: Неподдерживаемые функции Analysis Services в SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, backward compatibility
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
- discontinued functionality [Analysis Services]
- unsupported features [Analysis Services]
ms.assetid: 39406be1-9819-4629-9c29-b32fb20bab2e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5414344eb65c907593c9077ee2ba5610b8b397c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668501"
---
# <a name="discontinued-analysis-services-functionality-in-sql-server-2014"></a><span data-ttu-id="4063e-102">Неподдерживаемые функции служб Analysis Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4063e-102">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>
  <span data-ttu-id="4063e-103">В этой статье описаны функции служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которые больше недоступны в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4063e-103">This topic describes [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features that are no longer available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
## <a name="discontinued-features-in-sssql14"></a><span data-ttu-id="4063e-104">Неподдерживаемые функции в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4063e-104">Discontinued Features in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
  
|<span data-ttu-id="4063e-105">Категория</span><span class="sxs-lookup"><span data-stu-id="4063e-105">Category</span></span>|<span data-ttu-id="4063e-106">Устаревшая функция</span><span class="sxs-lookup"><span data-stu-id="4063e-106">Deprecated feature</span></span>|<span data-ttu-id="4063e-107">Замена</span><span class="sxs-lookup"><span data-stu-id="4063e-107">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="4063e-108">Локальные кубы</span><span class="sxs-lookup"><span data-stu-id="4063e-108">Local cubes</span></span>|<span data-ttu-id="4063e-109">InsertInto, свойство строки подключения</span><span class="sxs-lookup"><span data-stu-id="4063e-109">InsertInto connection string property</span></span>|<span data-ttu-id="4063e-110">Исходный синтаксис строки подключения для заполнения локальных кубов заменяется на инструкцию создания глобального куба.</span><span class="sxs-lookup"><span data-stu-id="4063e-110">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="4063e-111">Дополнительные сведения см. в разделе [инструкция CREATE GLOBAL CUBE &#40;&#41;многомерных выражений ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="4063e-111">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="4063e-112">Локальные кубы</span><span class="sxs-lookup"><span data-stu-id="4063e-112">Local cubes</span></span>|<span data-ttu-id="4063e-113">CreateCube, свойство строки подключения</span><span class="sxs-lookup"><span data-stu-id="4063e-113">CreateCube connection string property</span></span>|<span data-ttu-id="4063e-114">Исходный синтаксис строки подключения для заполнения локальных кубов заменяется на инструкцию создания глобального куба.</span><span class="sxs-lookup"><span data-stu-id="4063e-114">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="4063e-115">Дополнительные сведения см. в разделе [инструкция CREATE GLOBAL CUBE &#40;&#41;многомерных выражений ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="4063e-115">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="4063e-116">Интеллектуальный анализ данных</span><span class="sxs-lookup"><span data-stu-id="4063e-116">Data Mining</span></span>|<span data-ttu-id="4063e-117">SQL Server 2000 PMML</span><span class="sxs-lookup"><span data-stu-id="4063e-117">SQL Server 2000 PMML</span></span>|<span data-ttu-id="4063e-118">Компонент SQL Server 2000 PMML создавал форму PMML, содержащую расширения для поддержки уникальных возможностей, предоставляемых алгоритмами интеллектуального анализа данных, недоступными в спецификации PMML.</span><span class="sxs-lookup"><span data-stu-id="4063e-118">The SQL Server 2000 PMML feature produced a form of PMML that had proprietary extensions to support unique features provided by Data Mining algorithms that were not available in the PMML specification.</span></span> <span data-ttu-id="4063e-119">В SQL Server 2005 службы Analysis Services обновили компонент PMML до нового стандарта PMML 2.1.</span><span class="sxs-lookup"><span data-stu-id="4063e-119">In SQL Server 2005, Analysis Services updated the PMML feature to the newer PMML 2.1 standard.</span></span> <span data-ttu-id="4063e-120">В результате частные расширения, добавленные в SQL Server 2000, больше не нужны, несмотря на то что они по-прежнему поддерживаются в этом выпуске.</span><span class="sxs-lookup"><span data-stu-id="4063e-120">As a result, the proprietary extensions added in SQL Server 2000 are no longer needed, although they are still supported in this release.</span></span>|  
|<span data-ttu-id="4063e-121">Инструкция многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="4063e-121">MDX Statement</span></span>|<span data-ttu-id="4063e-122">Инструкция Create Action</span><span class="sxs-lookup"><span data-stu-id="4063e-122">Create Action statement</span></span>|<span data-ttu-id="4063e-123">Данная инструкция включена для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="4063e-123">This statement is included for backwards compatibility.</span></span> <span data-ttu-id="4063e-124">Заменена объектом Action.</span><span class="sxs-lookup"><span data-stu-id="4063e-124">It is replaced by the Action object.</span></span> <span data-ttu-id="4063e-125">Дополнительные сведения о создании действий в последних версиях [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] см. в разделе [actions &#40;Analysis Services-многомерные данные&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="4063e-125">For more information about how to create actions in recent versions of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="discontinued-features-in-previous-releases"></a><span data-ttu-id="4063e-126">Неподдерживаемые функции предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="4063e-126">Discontinued Features in Previous Releases</span></span>  
 <span data-ttu-id="4063e-127">Мастер миграции, использовавшийся для переноса баз данных SQL Server 2000 Analysis Services в новые версии, более не поддерживается, так как SQL Server 2000 более не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4063e-127">Migration Wizard, used to migrate SQL Server 2000 Analysis Services databases to newer versions, is discontinued because SQL Server 2000 is no longer supported.</span></span>  
  
 <span data-ttu-id="4063e-128">Библиотека объектов DSO, которая обеспечивала совместимость с базами данных SQL Server 2000 Analysis Services, также более не поддерживается и не является частью SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4063e-128">Decision Support Objects (DSO) library that provided compatibility with SQL Server 2000 Analysis Services databases is also discontinued and no longer part of SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4063e-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="4063e-129">See Also</span></span>  
 [<span data-ttu-id="4063e-130">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="4063e-130">Analysis Services Backward Compatibility</span></span>](analysis-services-backward-compatibility.md)  
  
  
