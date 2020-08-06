---
title: Источники данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733281"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="367fb-102">Источники данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="367fb-103">Источники данных предоставляют данные для включения в решения табличной модели.</span><span class="sxs-lookup"><span data-stu-id="367fb-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="367fb-104">Данные можно импортировать в модель из разных источников, таких как реляционные базы данных, веб-каналы данных, многомерные источники данных, например куб служб Analysis Services, а также данные из текстовых файлов, таких как книга Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="367fb-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="367fb-105">В темах настоящего раздела представлены сведения о типах источников данных, из которых можно выполнять импорт, различных типах импортируемых данных, а также о задачах, которые описывают импорт данных из этих источников данных.</span><span class="sxs-lookup"><span data-stu-id="367fb-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="367fb-106">Связанные темы и задачи</span><span class="sxs-lookup"><span data-stu-id="367fb-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="367fb-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="367fb-107">Topic</span></span>|<span data-ttu-id="367fb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="367fb-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="367fb-109">Поддерживаемые источники данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="367fb-110">Этот раздел содержит сведения об источниках данных, из которых можно импортировать данные.</span><span class="sxs-lookup"><span data-stu-id="367fb-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="367fb-111">Поддерживаемые типы данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="367fb-112">В этом разделе содержатся сведения о различных типах данных, поддерживаемых в табличной модели.</span><span class="sxs-lookup"><span data-stu-id="367fb-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="367fb-113">Олицетворение (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="367fb-114">В этом разделе приводятся сведения об олицетворении, т. е. предоставлении учетных данных входа в систему, используемых службами Analysis Services при соединении с источником данных для импорта и обновления данных.</span><span class="sxs-lookup"><span data-stu-id="367fb-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="367fb-115">Импорт данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="367fb-116">Задачи в этом разделе описывают, как импортировать данные из различных источников данных.</span><span class="sxs-lookup"><span data-stu-id="367fb-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="367fb-117">Обработка данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="367fb-118">Задачи в этом разделе описывают, как обработать (обновить) или изменить данные, которые уже были импортированы в модель.</span><span class="sxs-lookup"><span data-stu-id="367fb-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="367fb-119">Изменение существующего соединения с источником данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="367fb-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="367fb-120">Описывает изменение соединения с источником данных, которое уже было создано и используется для импорта данных из источника.</span><span class="sxs-lookup"><span data-stu-id="367fb-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  
