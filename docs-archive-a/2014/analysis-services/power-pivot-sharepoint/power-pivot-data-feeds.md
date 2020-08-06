---
title: Веб-каналы данных PowerPivot | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML data sources [Analysis Services with SharePoint]
- data feeds [Analysis Services with SharePoint]
- Atom data feeds
ms.assetid: 6b1337c5-50a0-4fc2-b079-377dc241d2cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3dd788c51867924882eba80fb9cbed280143fd6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667413"
---
# <a name="powerpivot-data-feeds"></a><span data-ttu-id="11c20-102">Веб-каналы данных PowerPivot</span><span class="sxs-lookup"><span data-stu-id="11c20-102">PowerPivot Data Feeds</span></span>
  <span data-ttu-id="11c20-103">По запросу канал данных предоставляет поток данных из источника данных в режиме «в сети» для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="11c20-103">A data feed provides a stream of data on demand from an online data source to a client application.</span></span> <span data-ttu-id="11c20-104">В [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]можно использовать каналы данных, чтобы добавлять данные из веб-службы или приложения с поддержкой потоков Atom в источник данных PowerPivot в книге Excel.</span><span class="sxs-lookup"><span data-stu-id="11c20-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use data feeds to add data from an Atom-aware Web service or application to a PowerPivot data source in an Excel workbook.</span></span>  
  
 <span data-ttu-id="11c20-105">В этом разделе приведены сведения, с помощью которых можно наиболее эффективно использовать потоки данных для передачи существующих корпоративных данных или данных рабочих групп в рабочие книги PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="11c20-105">This section provides information to help you make best use of data feeds to get existing corporate or workgroup data into PowerPivot workbooks.</span></span> <span data-ttu-id="11c20-106">Кроме того, даны сведения о предоставлении общего доступа для других пользователей к веб-каналам данных в организации, а также структуре веб-каналов данных и их использовании при необходимости диагностики и устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="11c20-106">It also provides information on how share data feeds with others in your organization, and how data feeds are constructed and used in case you need to troubleshoot any problems that arise.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="11c20-107">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="11c20-107">Related Tasks</span></span>  
 [<span data-ttu-id="11c20-108">Создание или Настройка библиотеки веб-каналов данных &#40;PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="11c20-108">Create or Customize a Data Feed Library &#40;PowerPivot for SharePoint&#41;</span></span>](create-or-customize-a-data-feed-library-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="11c20-109">Удаление библиотеки каналов данных PowerPivot</span><span class="sxs-lookup"><span data-stu-id="11c20-109">Delete a PowerPivot Data Feed Library</span></span>](delete-a-power-pivot-data-feed-library.md)  
  
 [<span data-ttu-id="11c20-110">Использование веб-каналов данных &#40;PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="11c20-110">Use Data Feeds &#40;PowerPivot for SharePoint&#41;</span></span>](use-data-feeds-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="11c20-111">Совместное использование веб-каналов данных с помощью библиотеки каналов данных &#40;PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="11c20-111">Share Data Feeds Using a Data Feed Library &#40;PowerPivot for SharePoint&#41;</span></span>](share-data-feeds-using-a-data-feed-library-power-pivot-for-sharepoint.md)  
  
  
