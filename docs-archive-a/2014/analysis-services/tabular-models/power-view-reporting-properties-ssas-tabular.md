---
title: Свойства отчетов Power View (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 51205c2d-b6ce-4b92-afd2-58e399a81691
author: minewiskan
ms.author: owend
ms.openlocfilehash: e85d91578e5c3f4b47f56eeb86aa738e37e8f59b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728774"
---
# <a name="power-view-reporting-properties-ssas-tabular"></a><span data-ttu-id="ec915-102">Свойства отчетов Power View (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ec915-102">Power View Reporting Properties (SSAS Tabular)</span></span>
  [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="ec915-103">представляет интуитивно понятный способ создания ad-hoc-отчетов для бизнес-пользователей — аналитиков, сотрудников, ответственных за принятие решений, и информационных работников.</span><span class="sxs-lookup"><span data-stu-id="ec915-103">provides intuitive ad-hoc reporting for business users such as data analysts, business decision makers, and information workers.</span></span> <span data-ttu-id="ec915-104">Они могут легко создавать представления данных из табличных моделей, основанных на книгах PowerPivot, которые опубликованы в галерее PowerPivot, или табличных моделей, созданных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] и затем развернутых в экземплярах служб [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services, и работать с ними.</span><span class="sxs-lookup"><span data-stu-id="ec915-104">They can easily create and interact with views of data from tabular models based on PowerPivot workbooks published in a PowerPivot Gallery, or tabular models authored by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and then deployed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services instances.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="ec915-105">— это браузерное приложение на основе Silverlight, запускаемое из SharePoint Server 2010 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ec915-105">is a browser-based Silverlight application launched from SharePoint Server 2010 or later.</span></span>  
  
 <span data-ttu-id="ec915-106">При создании проектов табличной модели в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]пользователь может настроить определенные свойства составления отчетов, которые будут уникальными для отчетов [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec915-106">When authoring tabular model projects in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can configure certain reporting properties unique to [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="ec915-107">В подразделах этого раздела описывается оптимизация модели с целью улучшения работы с отчетами в [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec915-107">Topics in this section describe how to optimize a model to improve the reporting experience in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ec915-108">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ec915-108">Related Tasks</span></span>  
  
|<span data-ttu-id="ec915-109">Раздел</span><span class="sxs-lookup"><span data-stu-id="ec915-109">Topic</span></span>|<span data-ttu-id="ec915-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ec915-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ec915-111">Настройка набора полей по умолчанию для отчетов Power View (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ec915-111">Configure Default Field Set for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-default-field-set-for-reports.md)|<span data-ttu-id="ec915-112">Описывает настройку набора полей по умолчанию, представляющего собой предопределенный список столбцов и мер, которые автоматически добавляются на лист отчета [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] при выборе таблицы из списка полей отчета.</span><span class="sxs-lookup"><span data-stu-id="ec915-112">Describes how to configure a Default Field Set; a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span>|  
|[<span data-ttu-id="ec915-113">Настройка свойств работы таблицы для отчетов Power View (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ec915-113">Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-table-behavior-properties-for-reports.md)|<span data-ttu-id="ec915-114">Описывает настройку свойств поведения таблицы, предлагающих более гранулярный уровень для строк сведений.</span><span class="sxs-lookup"><span data-stu-id="ec915-114">Describes how to configure table behavior properties that expose detail rows at a more granular level.</span></span> <span data-ttu-id="ec915-115">Задание свойств поведения таблицы изменяет режим группирования для строк сведений и обеспечивает более эффективное размещение идентификационных сведений в виде мозаики, карточек или диаграмм.</span><span class="sxs-lookup"><span data-stu-id="ec915-115">Setting table behavior properties changes the grouping behavior of detail rows and produces a better default placement of identifying information in tile, card, and chart layouts.</span></span>|  
  
  
