---
title: Упреждающее кэширование (измерения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], proactive caching
- proactive caching [Analysis Services]
ms.assetid: 7d57fe93-6e5f-4a50-844f-dd2bbdbb94a5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50c723d46b6c51fae0ccc227b5e58cf96f72c7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656020"
---
# <a name="proactive-caching-dimensions"></a><span data-ttu-id="bd59b-102">Упреждающее кэширование (измерения)</span><span class="sxs-lookup"><span data-stu-id="bd59b-102">Proactive Caching (Dimensions)</span></span>
  <span data-ttu-id="bd59b-103">Упреждающее кэширование позволяет автоматически создавать кэш MOLAP для объектов OLAP, а также управлять им.</span><span class="sxs-lookup"><span data-stu-id="bd59b-103">Proactive caching provides automatic MOLAP cache creation and management for OLAP objects.</span></span> <span data-ttu-id="bd59b-104">Кубы мгновенно реагируют на изменения, которые происходят с данными из базы данных, благодаря уведомлениям, получаемым от базы данных.</span><span class="sxs-lookup"><span data-stu-id="bd59b-104">The cubes immediately incorporate changes that are made to the data in the database, based upon notifications received from the database.</span></span> <span data-ttu-id="bd59b-105">Цель упреждающего кэширования — совмещение производительности, характерной для традиционного MOLAP, со скоростью и простотой управления ROLAP.</span><span class="sxs-lookup"><span data-stu-id="bd59b-105">The goal of proactive caching is to provide the performance of traditional MOLAP, while retaining the immediacy and ease of management offered by ROLAP.</span></span>  
  
 <span data-ttu-id="bd59b-106">Простой объект <xref:Microsoft.AnalysisServices.ProactiveCaching> содержит спецификации времени и уведомления таблиц.</span><span class="sxs-lookup"><span data-stu-id="bd59b-106">A simple <xref:Microsoft.AnalysisServices.ProactiveCaching> object is composed of: timing specification, and table notification.</span></span> <span data-ttu-id="bd59b-107">Спецификация времени определяет временной промежуток, за который кэш обновляется после получения уведомления об изменении.</span><span class="sxs-lookup"><span data-stu-id="bd59b-107">The timing specification defines the timeframe for updating the cache after a change notification has been received.</span></span> <span data-ttu-id="bd59b-108">В уведомлении таблиц определяется схема обмена уведомлениями между таблицей данных и объектом <xref:Microsoft.AnalysisServices.ProactiveCaching>.</span><span class="sxs-lookup"><span data-stu-id="bd59b-108">The table notification defines the notification schema between the data table and the <xref:Microsoft.AnalysisServices.ProactiveCaching> object.</span></span>  
  
  
