---
title: Табличное моделирование (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657323"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="2775e-102">Табличное моделирование (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="2775e-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="2775e-103">Табличные модели являются базами данных в памяти служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2775e-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="2775e-104">С помощью современных алгоритмов сжатия и многопоточного обработчика запросов подсистема аналитики в памяти xVelocity (VertiPaq) обеспечивает быстрый доступ к объектам табличной модели и данным через такие клиентские приложения для создания отчетов как Microsoft Excel и Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2775e-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="2775e-105">Табличные модели поддерживают доступ к данным в двух режимах: режим кэширования и режим прямых запросов.</span><span class="sxs-lookup"><span data-stu-id="2775e-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="2775e-106">В режиме кеширования можно интегрировать данные из многих источников, включая реляционные базы данных, веб-каналы данных и неструктурированные текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="2775e-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="2775e-107">В режиме прямых запросов можно обойти временную модель, дав возможность клиентским приложениям запрашивать данные непосредственно из источника (реляционный SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2775e-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="2775e-108">Табличные модели создаются в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] с использованием новых шаблонов проекта табличной модели.</span><span class="sxs-lookup"><span data-stu-id="2775e-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="2775e-109">Можно импортировать данные из нескольких источников, а затем дополнить модель, добавив связи, вычисляемые столбцы, меры, ключевые идентификаторы производительности и иерархии.</span><span class="sxs-lookup"><span data-stu-id="2775e-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="2775e-110">Затем модели можно развернуть на экземпляре служб Analysis Services, где клиентские приложения отчетности могут подключаться к ним.</span><span class="sxs-lookup"><span data-stu-id="2775e-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="2775e-111">Развернутыми моделями можно управлять в среде SQL Server Management Studio как многомерными моделями.</span><span class="sxs-lookup"><span data-stu-id="2775e-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="2775e-112">Также они могут быть секционированы для оптимизации обработки и защиты на уровне строк с помощью безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="2775e-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2775e-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2775e-113">In This Section</span></span>  
 [<span data-ttu-id="2775e-114">Решения табличных моделей (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="2775e-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="2775e-115">Базы данных табличной модели (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="2775e-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="2775e-116">Доступ к данным табличной модели</span><span class="sxs-lookup"><span data-stu-id="2775e-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
