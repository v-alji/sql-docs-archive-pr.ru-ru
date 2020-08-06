---
title: Страница "кэширование", общие наборы данных (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664029"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="7a94d-102">Страница «Кэширование», «Общие наборы данных» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="7a94d-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="7a94d-103">Страница «Свойства кэширования» используется для задания параметров кэширования общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a94d-104">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a94d-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a94d-105">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7a94d-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="7a94d-106">Навигация</span><span class="sxs-lookup"><span data-stu-id="7a94d-106">Navigation</span></span>  
 <span data-ttu-id="7a94d-107">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="7a94d-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="7a94d-108">Открытие страницы «Свойства кэширования» для общего набора данных</span><span class="sxs-lookup"><span data-stu-id="7a94d-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="7a94d-109">Откройте диспетчер отчетов и найдите отчет, для которого необходимо настроить свойства общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="7a94d-110">Подведите указатель к общему набору данных и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7a94d-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="7a94d-111">В раскрывающемся списке выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="7a94d-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="7a94d-112">Откроется страница свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="7a94d-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="7a94d-113">Перейдите на вкладку **Кэширование** .</span><span class="sxs-lookup"><span data-stu-id="7a94d-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a94d-114">Варианты</span><span class="sxs-lookup"><span data-stu-id="7a94d-114">Options</span></span>  
 <span data-ttu-id="7a94d-115">**Общий набор данных в кэше**</span><span class="sxs-lookup"><span data-stu-id="7a94d-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="7a94d-116">Помещает временную копию данных в кэш при первом открытии отчета, использующего этот общий набор данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="7a94d-117">Следующие пользователи, запускающие этот отчет в период кэширования, получают кэшированную копию данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="7a94d-118">Как правило, кэширование позволяет повысить производительность, поскольку вместо повторного выполнения запроса к набору данных возвращаются данные из кэша.</span><span class="sxs-lookup"><span data-stu-id="7a94d-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="7a94d-119">**Истечение срока действия кэша через определенное число минут**</span><span class="sxs-lookup"><span data-stu-id="7a94d-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="7a94d-120">Укажите количество минут, в течение которого должна сохраняться кэшированная копия данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="7a94d-121">Как только срок действия временной копии истекает, данные из кэша больше не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="7a94d-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="7a94d-122">При следующем открытии отчета, использующего общий набор данных, выполняется запрос к нему и сервер отчетов снова помещает копию обновленных данных в кэш.</span><span class="sxs-lookup"><span data-stu-id="7a94d-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="7a94d-123">**Истечение срока действия кэша по следующему расписанию**</span><span class="sxs-lookup"><span data-stu-id="7a94d-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="7a94d-124">Запланируйте момент времени, когда данные кэша станут недействительными и будут удалены из кэша.</span><span class="sxs-lookup"><span data-stu-id="7a94d-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="7a94d-125">Расписание может быть общим или заданным только для текущего общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="7a94d-126">**Расписание набора данных**</span><span class="sxs-lookup"><span data-stu-id="7a94d-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="7a94d-127">Укажите расписание, используемое только для этого набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="7a94d-128">**Общее расписание**</span><span class="sxs-lookup"><span data-stu-id="7a94d-128">**Shared schedule**</span></span>  
 <span data-ttu-id="7a94d-129">Укажите расписание, совместно используемое отчетами, подписками и другими общими наборами данных.</span><span class="sxs-lookup"><span data-stu-id="7a94d-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="7a94d-130">**Применить**</span><span class="sxs-lookup"><span data-stu-id="7a94d-130">**Apply**</span></span>  
 <span data-ttu-id="7a94d-131">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="7a94d-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a94d-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a94d-132">See Also</span></span>  
 <span data-ttu-id="7a94d-133">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="7a94d-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="7a94d-134">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7a94d-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="7a94d-135">[Общие наборы данных кэша &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a94d-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="7a94d-136">Расписания</span><span class="sxs-lookup"><span data-stu-id="7a94d-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
