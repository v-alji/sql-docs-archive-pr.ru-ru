---
title: Предварительная загрузка кэша (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732406"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="fffea-102">выполнить предварительную загрузку кэша (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="fffea-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="fffea-103">Можно предварительно загрузить кэш для общего набора данных путем создания плана обновления кэша для общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="fffea-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="fffea-104">Предварительно загрузить кэш для отчета можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="fffea-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="fffea-105">Создать плана обновления кэша для отчета.</span><span class="sxs-lookup"><span data-stu-id="fffea-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="fffea-106">Это является предпочтительным методом.</span><span class="sxs-lookup"><span data-stu-id="fffea-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="fffea-107">Используйте управляемую данными подписку для предварительной загрузки в кэш экземпляров параметризованных отчетов.</span><span class="sxs-lookup"><span data-stu-id="fffea-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="fffea-108">В версиях служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , предшествующих [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], это был единственный способ предварительной загрузки кэша.</span><span class="sxs-lookup"><span data-stu-id="fffea-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="fffea-109">Дополнительные сведения см. в разделе [Кэширование отчетов (службы SSRS)](caching-reports-ssrs.md), это был единственный способ предварительной загрузки кэша.</span><span class="sxs-lookup"><span data-stu-id="fffea-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="fffea-110">Прежде чем появится возможность кэшировать отчет или общий набор данных, должны быть выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="fffea-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="fffea-111">Для общего набора данных или отчета должно быть включено кэширование.</span><span class="sxs-lookup"><span data-stu-id="fffea-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="fffea-112">Общие источники данных для общего набора данных или отчета должны быть настроены для использования сохраненных учетных данных или на работу без учетных данных.</span><span class="sxs-lookup"><span data-stu-id="fffea-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="fffea-113">Должна быть запущена служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fffea-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="fffea-114">Предварительная загрузка кэша путем создания плана обновления кэша</span><span class="sxs-lookup"><span data-stu-id="fffea-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="fffea-115">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fffea-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="fffea-116">В диспетчере отчетов перейдите на страницу **Содержимое** , а затем к элементу, который необходимо кэшировать.</span><span class="sxs-lookup"><span data-stu-id="fffea-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="fffea-117">Подведите курсор к элементу, щелкните раскрывающийся список, а затем щелкните **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fffea-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="fffea-118">Перейдите на вкладку **Параметры обновления кэша** .</span><span class="sxs-lookup"><span data-stu-id="fffea-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="fffea-119">На панели инструментов нажмите кнопку **Новый план обновления кэша**.</span><span class="sxs-lookup"><span data-stu-id="fffea-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fffea-120">Если для элемента не включено кэширование, то появится приглашение включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="fffea-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="fffea-121">Чтобы включать кэширование, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fffea-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="fffea-122">Откроется страница «План обновления кэша».</span><span class="sxs-lookup"><span data-stu-id="fffea-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="fffea-123">Дополнительно можно ввести описание плана обновления.</span><span class="sxs-lookup"><span data-stu-id="fffea-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="fffea-124">Для общего расписания нажмите кнопку **Общее расписание**, а затем выберите имя используемого расписания.</span><span class="sxs-lookup"><span data-stu-id="fffea-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="fffea-125">Применительно к пользовательскому расписанию щелкните **Расписание по элементам**, а затем — **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="fffea-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fffea-126">Настройка расписания</span><span class="sxs-lookup"><span data-stu-id="fffea-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="fffea-127">Предварительная загрузка в кэш отчета для конкретного пользователя с использованием управляемой данными подписки</span><span class="sxs-lookup"><span data-stu-id="fffea-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="fffea-128">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fffea-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="fffea-129">В диспетчере отчетов перейдите на страницу **Содержимое** , а затем перейдите к отчету, для которого необходимо создать подписку.</span><span class="sxs-lookup"><span data-stu-id="fffea-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="fffea-130">Щелкните отчет, перейдите на вкладку **Подписки** и нажмите кнопку **Создать управляемую данными подписку**.</span><span class="sxs-lookup"><span data-stu-id="fffea-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="fffea-131">Дополнительно можно ввести описание подписки.</span><span class="sxs-lookup"><span data-stu-id="fffea-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="fffea-132">Из списка **Укажите способ извещения получателей** , выберите пункт **Отсутствующий поставщик доставки**.</span><span class="sxs-lookup"><span data-stu-id="fffea-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="fffea-133">Укажите тип источника данных, затем нажмите кнопку **Далее** для настройки источника данных.</span><span class="sxs-lookup"><span data-stu-id="fffea-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="fffea-134">Укажите тип соединения, строку соединения и учетные данные для доступа к источнику данных, который содержит данные подписчика.</span><span class="sxs-lookup"><span data-stu-id="fffea-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="fffea-135">Следующий пример иллюстрирует строку соединения с именем «Subscribers», которая используется для соединения с базой данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="fffea-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="fffea-136">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fffea-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="fffea-137">Укажите запрос или команду, извлекающую данные подписчиков.</span><span class="sxs-lookup"><span data-stu-id="fffea-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="fffea-138">При необходимости увеличьте время ожидания для запросов, обработка которых занимает значительный период времени.</span><span class="sxs-lookup"><span data-stu-id="fffea-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="fffea-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="fffea-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="fffea-140">Нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="fffea-140">Click **Validate**.</span></span> <span data-ttu-id="fffea-141">Перед продолжением необходимо выполнить проверку запроса.</span><span class="sxs-lookup"><span data-stu-id="fffea-141">The query must be validated before you continue.</span></span> <span data-ttu-id="fffea-142">При появлении сообщения **Проверка завершена успешно** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fffea-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="fffea-143">Так как нельзя выбрать конфигурацию параметров настройки модуля доставки при отсутствующем поставщике доставки, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fffea-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="fffea-144">Укажите значения параметров отчета для подписки и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fffea-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="fffea-145">Укажите время обработки подписки.</span><span class="sxs-lookup"><span data-stu-id="fffea-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="fffea-146">Не выбирайте **При обновлении данных отчета на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="fffea-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="fffea-147">Этот параметр используется только для моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="fffea-147">That setting is for snapshots only.</span></span> <span data-ttu-id="fffea-148">Если нужно использовать уже существующее расписание, выберите **По общему расписанию**.</span><span class="sxs-lookup"><span data-stu-id="fffea-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="fffea-149">Или нажмите **По расписанию, созданному для этой подписки** для создания пользовательского расписания, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fffea-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="fffea-150">Настройте расписание, затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fffea-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fffea-151">Чтобы подписчики получили самый новый отчет, настраиваемое расписание должно быть согласовано с расписанием доставки отчета, которое определено для подписчиков.</span><span class="sxs-lookup"><span data-stu-id="fffea-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="fffea-152">Дополнительные сведения см. в разделе [Диспетчер отчетов (службы SSRS в собственном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fffea-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="fffea-153">Настройте параметры выполнения отчета следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fffea-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="fffea-154">На странице отчета перейдите на вкладку **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="fffea-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="fffea-155">В левом окне перейдите на вкладку **Выполнение** .</span><span class="sxs-lookup"><span data-stu-id="fffea-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="fffea-156">На этой странице выберите **Подготовить отчет с применением самых последних данных**.</span><span class="sxs-lookup"><span data-stu-id="fffea-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="fffea-157">Выберите один из следующих двух режимов кэша и настройте время истечения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fffea-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="fffea-158">Чтобы срок действия кэшированной копии истек через определенное время, выберите **Кэшировать временную копию отчета. Срок действия копии отчета заканчивается через несколько минут**.</span><span class="sxs-lookup"><span data-stu-id="fffea-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="fffea-159">Введите срок действия отчета (в минутах).</span><span class="sxs-lookup"><span data-stu-id="fffea-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="fffea-160">Чтобы срок действия кэшированной копии истек в соответствии с расписанием, выберите **Кэшировать временную копию отчета. Срок действия копии отчета истекает в соответствии со следующим расписанием**.</span><span class="sxs-lookup"><span data-stu-id="fffea-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="fffea-161">Нажмите кнопку **Настроить**или выберите общее расписание для настройки истечения срока действия отчета.</span><span class="sxs-lookup"><span data-stu-id="fffea-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="fffea-162">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fffea-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fffea-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="fffea-163">See Also</span></span>  
 <span data-ttu-id="fffea-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="fffea-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="fffea-165">[Создание управляемой данными подписки (учебник по службам SSRS)](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="fffea-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="fffea-166">[Производительность, моментальные снимки, кэширование &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="fffea-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="fffea-167">[Установка свойств обработки отчета](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fffea-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="fffea-168">Кэширование отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="fffea-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
