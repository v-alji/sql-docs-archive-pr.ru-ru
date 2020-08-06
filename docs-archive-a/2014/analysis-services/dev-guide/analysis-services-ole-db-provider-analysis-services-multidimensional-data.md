---
title: Поставщик Analysis Services OLE DB (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services OLE DB Provider
ms.assetid: cdeecd50-1d91-4162-a4a2-01c7799b02a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c0348a23a6def4c3cdbd083354083947ce1390b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669164"
---
# <a name="analysis-services-ole-db-provider-analysis-services---multidimensional-data"></a><span data-ttu-id="3ce5f-102">Поставщик OLE DB служб Analysis Services (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="3ce5f-102">Analysis Services OLE DB Provider (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3ce5f-103">Поставщик Analysis Services OLE DB — это интерфейс для приложений, взаимодействующих с [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ce5f-103">The Analysis Services OLE DB Provider is an interface for applications interacting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="3ce5f-104">Используется для построения клиентских приложений, взаимодействующих с многомерными данными.</span><span class="sxs-lookup"><span data-stu-id="3ce5f-104">It is used to build client applications that interact with multidimensional data.</span></span> <span data-ttu-id="3ce5f-105">Этот поставщик также предоставляет методы для интеллектуального анализа многомерных данных и реляционных данных как в сети, так и вне сети. Поставляется в составе служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ce5f-105">This provider also provides methods for online and offline data mining analysis of multidimensional data and relational data, and is included as part of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="3ce5f-106">Его можно распространять в сторонних клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="3ce5f-106">It can be redistributed by third-party client applications.</span></span>  
  
 <span data-ttu-id="3ce5f-107">Поставщик OLE DB служб Analysis Services — это основной метод взаимодействия со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для выполнения таких задач, как соединение с кубом или моделью интеллектуального анализа данных, направление запросов к кубу или модели интеллектуального анализа данных и получение сведений о схеме.</span><span class="sxs-lookup"><span data-stu-id="3ce5f-107">The Analysis Services OLE DB Provider is the primary method for interacting with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in order to accomplish such tasks as connecting to a cube or data mining model, querying a cube or data mining model, and retrieving schema information.</span></span>  
  
 <span data-ttu-id="3ce5f-108">В качестве изолированного поставщика поставщик OLE DB служб Analysis Services предоставляет клиентским приложениям возможность создавать файлы локальных кубов и модели интеллектуального анализа данных из реляционных и многомерных источников.</span><span class="sxs-lookup"><span data-stu-id="3ce5f-108">As a stand-alone provider, the Analysis Services OLE DB Provider provides client applications with the ability to create local cube files and mining models from relational and multidimensional sources.</span></span> <span data-ttu-id="3ce5f-109">Клиентские приложения могут соединяться с локальным кубом и выполнять запросы с многомерными выражениями, без взаимодействия с полномасштабным сервером, который работает с экземпляром служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ce5f-109">Client applications can connect to a local cube and execute queries using Multidimensional Expressions (MDX) without interacting with the full-scale server running the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce5f-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="3ce5f-110">See Also</span></span>  
 [<span data-ttu-id="3ce5f-111">Доступ к данным многомерной модели &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="3ce5f-111">Multidimensional Model Data Access &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/mdx/multidimensional-model-data-access-analysis-services-multidimensional-data.md)  
  
  
