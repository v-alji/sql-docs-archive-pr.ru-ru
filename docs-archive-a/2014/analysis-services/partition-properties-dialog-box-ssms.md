---
title: Диалоговое окно «Свойства секции» (SSMS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionpropertiesdialog.f1
ms.assetid: dfb5b7a0-7543-4e5e-8a30-4b734606e157
author: minewiskan
ms.author: owend
ms.openlocfilehash: b606a39ef99e5313b526ab0210448e295c5f04cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727393"
---
# <a name="partition-properties-dialog-box-ssms"></a><span data-ttu-id="7443c-102">Диалоговое окно «Свойства секции» (среда SSMS)</span><span class="sxs-lookup"><span data-stu-id="7443c-102">Partition Properties Dialog Box (SSMS)</span></span>
  <span data-ttu-id="7443c-103">Диалоговое окно **Свойства секции** среды SQL Server Management Studio позволяет задать свойства секции для куба в базе данных служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7443c-103">Use the **Partition Properties** dialog box in SQL Server Management Studio to set the properties of a partition for a cube in an [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="7443c-104">Чтобы открыть диалоговое окно **Свойства секции** , в **Обозревателе объектов**щелкните правой кнопкой мыши секцию и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7443c-104">To open the **Partition Properties** dialog box, in **Object Explorer**, right-click a partition, and then click **Properties**.</span></span>  
  
 <span data-ttu-id="7443c-105">В диалоговом окне **Свойства секции** содержатся следующие страницы.</span><span class="sxs-lookup"><span data-stu-id="7443c-105">The **Partition Properties** dialog box contains the following pages:</span></span>  
  
## <a name="pages"></a><span data-ttu-id="7443c-106">Страницы</span><span class="sxs-lookup"><span data-stu-id="7443c-106">Pages</span></span>  
  
|<span data-ttu-id="7443c-107">Страница</span><span class="sxs-lookup"><span data-stu-id="7443c-107">Page</span></span>|<span data-ttu-id="7443c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7443c-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7443c-109">**Выбор**</span><span class="sxs-lookup"><span data-stu-id="7443c-109">**Selection**</span></span>|<span data-ttu-id="7443c-110">На странице **Выбор** можно выбрать секцию в группе мер, свойства которой нужно просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="7443c-110">Use the **Selection** page to select the partition in the measure group for which you want to display or modify properties.</span></span> <span data-ttu-id="7443c-111">Дополнительные сведения об этой странице см. в разделе [Выбор (диалоговое окно "Свойства секции") (среда SSMS)](selection-partition-properties-dialog-box-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="7443c-111">For more information about this page, see [Selection &#40;Partition Properties Dialog Box&#41; &#40;SSMS&#41;](selection-partition-properties-dialog-box-ssms.md).</span></span>|  
|<span data-ttu-id="7443c-112">**Общие**</span><span class="sxs-lookup"><span data-stu-id="7443c-112">**General**</span></span>|<span data-ttu-id="7443c-113">На странице **Общие** можно просмотреть и изменить общие свойства секции, выбранной на странице **Выбор** .</span><span class="sxs-lookup"><span data-stu-id="7443c-113">Use the **General** page to display and modify the general properties of the partition selected in the **Selection** page.</span></span> <span data-ttu-id="7443c-114">Дополнительные сведения об этой странице см. в разделе [Общие (диалоговое окно "Свойства секции") (среда SSMS)](general-partition-properties-dialog-box-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="7443c-114">For more information about this page, see [General &#40;Partition Properties Dialog Box&#41; &#40;SSMS&#41;](general-partition-properties-dialog-box-ssms.md).</span></span>|  
|<span data-ttu-id="7443c-115">**Упреждающее кэширование**</span><span class="sxs-lookup"><span data-stu-id="7443c-115">**Proactive Caching**</span></span>|<span data-ttu-id="7443c-116">На странице **Упреждающее кэширование** можно просмотреть и изменить настройки хранения и упреждающего кэширования для секции, выбранной на странице **Выбор** .</span><span class="sxs-lookup"><span data-stu-id="7443c-116">Use the **Proactive Caching** page to display and modify the storage and proactive caching settings of the partition selected in the **Selection** page.</span></span> <span data-ttu-id="7443c-117">Дополнительные сведения об этой странице см. в разделе [Упреждающее кэширование (диалоговое окно "Свойства секции") (среда SSMS)](proactive-caching-partition-properties-dialog-box-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="7443c-117">For more information about this page, see [Proactive Caching &#40;Partition Properties Dialog Box&#41; &#40;SSMS&#41;](proactive-caching-partition-properties-dialog-box-ssms.md).</span></span>|  
|<span data-ttu-id="7443c-118">**Конфигурация ошибок**</span><span class="sxs-lookup"><span data-stu-id="7443c-118">**Error Configuration**</span></span>|<span data-ttu-id="7443c-119">На странице **Конфигурация ошибок** можно просмотреть и изменить настройки конфигурации ошибок при обработке секции, выбранной на странице **Выбор** .</span><span class="sxs-lookup"><span data-stu-id="7443c-119">Use the **Error Configuration** page to display and modify the error configuration settings for processing the partition selected in the **Selection** page.</span></span> <span data-ttu-id="7443c-120">Дополнительные сведения об этой странице см. в разделе [Конфигурация ошибок при обработке кубов, секций и измерений (службы SSAS — многомерные данные)](multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md).</span><span class="sxs-lookup"><span data-stu-id="7443c-120">For more information about this page, see [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7443c-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7443c-121">See Also</span></span>  
 <span data-ttu-id="7443c-122">[Секции &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7443c-122">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7443c-123">[Удаленные секции](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md) </span><span class="sxs-lookup"><span data-stu-id="7443c-123">[Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md) </span></span>  
 [<span data-ttu-id="7443c-124">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7443c-124">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
