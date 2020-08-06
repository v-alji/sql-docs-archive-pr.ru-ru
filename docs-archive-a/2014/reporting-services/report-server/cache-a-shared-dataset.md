---
title: Кэширование общих наборов данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665827"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="3d26e-102">кэшировать общий набор данных</span><span class="sxs-lookup"><span data-stu-id="3d26e-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="3d26e-103">Один из способов повышения производительности состоит в настройке свойств кэширования общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="3d26e-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="3d26e-104">При кэшировании общего набора данных копия результатов запроса сохраняется на указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="3d26e-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="3d26e-105">Первый пользователь, запрашивающий отчет, в котором используется общий набор данных, должен будет дождаться получения результатов запроса и завершения всех процессов обработки до просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="3d26e-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="3d26e-106">Производительность работы последующих пользователей, запрашивающих тот же отчет в пределах времени кэширования, будет значительно повышена, поскольку запрос и обработка уже выполнены.</span><span class="sxs-lookup"><span data-stu-id="3d26e-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="3d26e-107">Также можно указать расписание обновления кэша для выполнения запроса и кэширования результатов до истечения указанного периода кэширования.</span><span class="sxs-lookup"><span data-stu-id="3d26e-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="3d26e-108">Пользователи, выполняющие отчеты на основе общих наборов данных или планов обновления кэша, создают кэш запроса, и в обоих случаях доступность кэша зависит от параметров периода истечения кэша.</span><span class="sxs-lookup"><span data-stu-id="3d26e-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="3d26e-109">Существуют ограничения на типы общих наборов, которые можно кэшировать.</span><span class="sxs-lookup"><span data-stu-id="3d26e-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="3d26e-110">Например, результаты запроса нельзя кэшировать, если данные зависят от идентификатора пользователя или если данные получаются с помощью токена безопасности пользователя, запросившего отчет.</span><span class="sxs-lookup"><span data-stu-id="3d26e-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="3d26e-111">Дополнительные сведения см. в разделах [Общие наборы данных в кэше (службы SSRS)](cache-shared-datasets-ssrs.md) и [Кэширование отчетов (службы SSRS)](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d26e-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="3d26e-112">Назначение момента для истечения срока действия кэшированного отчета</span><span class="sxs-lookup"><span data-stu-id="3d26e-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="3d26e-113">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3d26e-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="3d26e-114">В диспетчере отчетов перейдите к общему набору данных, для которого необходимо задать свойства кэширования, наведите на него курсор мыши и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3d26e-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="3d26e-115">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="3d26e-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="3d26e-116">В левом окне перейдите на вкладку **Кэширование**.</span><span class="sxs-lookup"><span data-stu-id="3d26e-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d26e-117">При возникновении ошибки **Не сохранены учетные данные, используемые для выполнения общего набора данных**параметры кэширования для общего набора данных будут отключены.</span><span class="sxs-lookup"><span data-stu-id="3d26e-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="3d26e-118">Необходимо изменить источник данных, хранящий учетные данные, или изменить общий набор данных для использования другого источника данных, хранящего учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3d26e-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="3d26e-119">Выберите **Кэширование общего набора данных**.</span><span class="sxs-lookup"><span data-stu-id="3d26e-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="3d26e-120">Установите для параметра истечения срока действия кэша значение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3d26e-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="3d26e-121">Также можно выбрать истечения срока действия кэша по указанному расписанию.</span><span class="sxs-lookup"><span data-stu-id="3d26e-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="3d26e-122">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="3d26e-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d26e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d26e-123">See Also</span></span>  
 [<span data-ttu-id="3d26e-124">Управление общими наборами данных</span><span class="sxs-lookup"><span data-stu-id="3d26e-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
