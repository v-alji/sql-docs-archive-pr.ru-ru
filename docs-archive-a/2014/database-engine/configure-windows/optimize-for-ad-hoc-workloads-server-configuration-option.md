---
title: Параметр конфигурации сервера "optimize for ad hoc workloads" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729802"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="3179e-102">Параметр конфигурации сервера «optimize for ad hoc workloads»</span><span class="sxs-lookup"><span data-stu-id="3179e-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="3179e-103">Параметр **optimize for ad hoc workloads** используется для повышения эффективности кэширования планов рабочих нагрузок, содержащих много отдельных нерегламентированных пакетов.</span><span class="sxs-lookup"><span data-stu-id="3179e-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="3179e-104">Если этот параметр имеет значение 1, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] при первой компиляции пакета сохраняет в кэше планов небольшую скомпилированную заглушку плана, а не полный откомпилированный план.</span><span class="sxs-lookup"><span data-stu-id="3179e-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="3179e-105">Это несколько снижает требования к памяти, так как кэш планов не заполняется скомпилированными, не используемыми повторно планами.</span><span class="sxs-lookup"><span data-stu-id="3179e-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="3179e-106">Откомпилированная заглушка плана позволяет компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] понять, что данный нерегламентированный пакет компилировался ранее, но от него сохранилась только заглушка. При повторном вызове этого пакета для компиляции или выполнения компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] откомпилирует пакет, удалит из кэша планов откомпилированную заглушку плана и добавит туда полный скомпилированный план.</span><span class="sxs-lookup"><span data-stu-id="3179e-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="3179e-107">Когда параметру **optimize for ad hoc workloads** присваивается значение 1, это влияет только на новые планы; те планы, которые уже находятся в кэше планов, остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="3179e-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="3179e-108">Скомпилированная заглушка плана принадлежит к объектам cacheobjtypes, которые можно просмотреть в представлении каталога sys.dm_exec_cached_plans.</span><span class="sxs-lookup"><span data-stu-id="3179e-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="3179e-109">У каждой заглушки есть уникальный дескриптор SQL и дескриптор плана.</span><span class="sxs-lookup"><span data-stu-id="3179e-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="3179e-110">Со скомпилированной заглушкой плана не связан план выполнения. Запрос по дескриптору плана не вернет XML-код Showplan.</span><span class="sxs-lookup"><span data-stu-id="3179e-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="3179e-111">Флаг трассировки 8032 восстанавливает параметры предела кэша до значения в RTM-версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , что обычно позволяет увеличить размер кэша.</span><span class="sxs-lookup"><span data-stu-id="3179e-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="3179e-112">Используйте этот параметр, если часто используемые повторно записи кэша не помещаются в кэш и параметру конфигурации сервера *Оптимизировать для нерегламентированной рабочей нагрузки* не удалось разрешить эту проблему с помощью кэша планов.</span><span class="sxs-lookup"><span data-stu-id="3179e-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3179e-113">Применение флага трассировки 8032 может привести к снижению производительности, если увеличение кэша приводит к уменьшению объема памяти, доступной для других потребителей памяти, например для буферного пула.</span><span class="sxs-lookup"><span data-stu-id="3179e-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3179e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="3179e-114">See Also</span></span>  
 <span data-ttu-id="3179e-115">[sys.dm_exec_cached_plans (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3179e-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="3179e-116">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3179e-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
