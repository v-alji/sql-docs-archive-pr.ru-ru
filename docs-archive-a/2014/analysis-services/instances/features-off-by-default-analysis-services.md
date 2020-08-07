---
title: Функции отключены по умолчанию (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731065"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="609b7-102">Возможности, отключенные по умолчанию (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="609b7-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="609b7-103">Экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] по умолчанию поддерживает параметры, обеспечивающие его безопасность.</span><span class="sxs-lookup"><span data-stu-id="609b7-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="609b7-104">Следовательно, функции, которые способны снизить безопасность, по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="609b7-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="609b7-105">Следующие функции установлены в отключенном состоянии. Чтобы их использовать, их нужно специально включить.</span><span class="sxs-lookup"><span data-stu-id="609b7-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="609b7-106">Список функций</span><span class="sxs-lookup"><span data-stu-id="609b7-106">Feature List</span></span>  
 <span data-ttu-id="609b7-107">Чтобы включить следующие функции, подключитесь к [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="609b7-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="609b7-108">Правой кнопкой мыши щелкните имя экземпляра и выберите пункт **Аспекты**.</span><span class="sxs-lookup"><span data-stu-id="609b7-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="609b7-109">Или можно воспользоваться свойствами сервера, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="609b7-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="609b7-110">Нерегламентированные запросы интеллектуального анализа данных (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="609b7-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="609b7-111">Связанные объекты (к)</span><span class="sxs-lookup"><span data-stu-id="609b7-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="609b7-112">Связанные объекты (от)</span><span class="sxs-lookup"><span data-stu-id="609b7-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="609b7-113">Прослушивание только локальных соединений</span><span class="sxs-lookup"><span data-stu-id="609b7-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="609b7-114">Определенные пользователем функции</span><span class="sxs-lookup"><span data-stu-id="609b7-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="609b7-115">Свойства сервера</span><span class="sxs-lookup"><span data-stu-id="609b7-115">Server properties</span></span>  
 <span data-ttu-id="609b7-116">Дополнительные отключенные по умолчанию функции можно включить с помощью свойств сервера.</span><span class="sxs-lookup"><span data-stu-id="609b7-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="609b7-117">Подключитесь к [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="609b7-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="609b7-118">Правой кнопкой мыши щелкните имя экземпляра и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="609b7-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="609b7-119">Щелкните **Общие**, а затем щелкните **Показать дополнительные** , чтобы отобразить длинный список свойств.</span><span class="sxs-lookup"><span data-stu-id="609b7-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="609b7-120">Нерегламентированные запросы интеллектуального анализа данных (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="609b7-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="609b7-121">Разрешить сеансные модели интеллектуального анализа данных (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="609b7-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="609b7-122">Связанные объекты (к)</span><span class="sxs-lookup"><span data-stu-id="609b7-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="609b7-123">Связанные объекты (от)</span><span class="sxs-lookup"><span data-stu-id="609b7-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="609b7-124">Определенные пользователем функции на базе COM</span><span class="sxs-lookup"><span data-stu-id="609b7-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="609b7-125">Определения отслеживаний «черного ящика» (шаблоны).</span><span class="sxs-lookup"><span data-stu-id="609b7-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="609b7-126">Ведение журнала запросов</span><span class="sxs-lookup"><span data-stu-id="609b7-126">Query logging</span></span>  
  
-   <span data-ttu-id="609b7-127">Прослушивание только локальных соединений</span><span class="sxs-lookup"><span data-stu-id="609b7-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="609b7-128">Двоичный XML-файл</span><span class="sxs-lookup"><span data-stu-id="609b7-128">Binary XML</span></span>  
  
-   <span data-ttu-id="609b7-129">Сжатие</span><span class="sxs-lookup"><span data-stu-id="609b7-129">Compression</span></span>  
  
-   <span data-ttu-id="609b7-130">Групповая схожесть.</span><span class="sxs-lookup"><span data-stu-id="609b7-130">Group affinity.</span></span> <span data-ttu-id="609b7-131">Дополнительные сведения см. в разделе [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="609b7-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
