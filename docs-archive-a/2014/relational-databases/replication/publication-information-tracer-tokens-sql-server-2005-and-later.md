---
title: Сведения о публикации, трассировочные токены (публикация транзакций, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736177"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="f184c-102">Сведения о публикации, трассировочные токены (публикация транзакций, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="f184c-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f184c-103"> На вкладке **Трассировочные токены** можно проверить соединения и измерить задержку системы, в которой используется репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="f184c-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="f184c-104">Токен (небольшой объем данных) записывается в журнал транзакций базы данных публикации и помечается так, как если бы он был обычной реплицируемой транзакцией, а затем проходит по системе, позволяя вычислить следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="f184c-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="f184c-105">Время, прошедшее между фиксацией транзакции на издателе и вставкой соответствующей команды в базу данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="f184c-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="f184c-106">Время, прошедшее между вставкой команды в базу данных распространителя и соответствующей транзакцией, зафиксированной у подписчика.</span><span class="sxs-lookup"><span data-stu-id="f184c-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="f184c-107">Из этих вычислений можно получить ответы на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="f184c-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="f184c-108">Какой подписчик позднее всех получает изменения от издателя?</span><span class="sxs-lookup"><span data-stu-id="f184c-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="f184c-109">Какие подписчики, ожидающие получение трассировочного токена, его не получили (если таковые имеются)?</span><span class="sxs-lookup"><span data-stu-id="f184c-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="f184c-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="f184c-110">Options</span></span>  
 <span data-ttu-id="f184c-111">Чтобы изменить способ отображения данных в сетке, щелкните правой кнопкой мыши сетку, а затем один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="f184c-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="f184c-112">**Сортировать**: сортировка по одному или нескольким столбцам в диалоговом окне **Сортировка столбцов** .</span><span class="sxs-lookup"><span data-stu-id="f184c-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f184c-113">**Выберите столбцы для отображения**: выбор столбцов для отображения и порядка их отображения в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="f184c-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f184c-114">**Фильтр**: фильтрация строк в сетке на основании значений столбцов в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="f184c-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="f184c-115">**Очистить фильтр**: удаление всех параметров фильтра для сетки.</span><span class="sxs-lookup"><span data-stu-id="f184c-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="f184c-116">Настройки фильтра уникальны для каждой сетки.</span><span class="sxs-lookup"><span data-stu-id="f184c-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="f184c-117">Выбор и сортировка столбцов применяются ко всем сеткам одного типа, как, например, сетка публикаций для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="f184c-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="f184c-118">**Вставить трассировочный маркер**</span><span class="sxs-lookup"><span data-stu-id="f184c-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="f184c-119">Выберите этот пункт, чтобы вставить трассировочный токен в журнал транзакций у издателя.</span><span class="sxs-lookup"><span data-stu-id="f184c-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="f184c-120">**Время вставки**</span><span class="sxs-lookup"><span data-stu-id="f184c-120">**Time inserted**</span></span>  
 <span data-ttu-id="f184c-121">Выберите время вставки трассировочного токена. Данные задержки будут выводиться, начиная с этого момента.</span><span class="sxs-lookup"><span data-stu-id="f184c-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="f184c-122">По умолчанию выводятся данные с самым поздним временем.</span><span class="sxs-lookup"><span data-stu-id="f184c-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f184c-123">Данные трассировочных токенов хранятся в течение того же периода времени, что и другие данные предыстории; этот период определяется сроком хранения журнала в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="f184c-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="f184c-124">Дополнительные сведения о доступе к этим диалоговым окнам см. в статье [Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f184c-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="f184c-125">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="f184c-125">**Subscription**</span></span>  
 <span data-ttu-id="f184c-126">Имя каждой подписки на публикацию.</span><span class="sxs-lookup"><span data-stu-id="f184c-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="f184c-127">**От издателя к распространителю**</span><span class="sxs-lookup"><span data-stu-id="f184c-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="f184c-128">Время, прошедшее между фиксацией транзакции на издателе и вставкой соответствующей команды в базу данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="f184c-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="f184c-129">Значение **Ожидание** указывает, что токен еще не достиг распространителя.</span><span class="sxs-lookup"><span data-stu-id="f184c-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="f184c-130">Если состояние ожидания не меняется, убедитесь, что запущен агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="f184c-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="f184c-131">**От распространителя к подписчику**</span><span class="sxs-lookup"><span data-stu-id="f184c-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="f184c-132">Время, прошедшее между вставкой команды в базу данных распространителя и соответствующей транзакцией, зафиксированной на подписчике.</span><span class="sxs-lookup"><span data-stu-id="f184c-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="f184c-133">Значение **Ожидание** указывает, что токен еще не достиг подписчика.</span><span class="sxs-lookup"><span data-stu-id="f184c-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="f184c-134">Если состояние ожидания не меняется, убедитесь, что запущен агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="f184c-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="f184c-135">**Total Latency (Общая задержка)**</span><span class="sxs-lookup"><span data-stu-id="f184c-135">**Total Latency**</span></span>  
 <span data-ttu-id="f184c-136">Время, прошедшее между фиксацией транзакции у издателя и фиксацией соответствующей транзакции у подписчика.</span><span class="sxs-lookup"><span data-stu-id="f184c-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="f184c-137">Это значение является совокупной задержкой системы репликации для этого подписчика на данный момент.</span><span class="sxs-lookup"><span data-stu-id="f184c-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="f184c-138">Значение **Ожидание** указывает, что токен еще не достиг подписчика.</span><span class="sxs-lookup"><span data-stu-id="f184c-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f184c-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="f184c-139">See Also</span></span>  
 <span data-ttu-id="f184c-140">[Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f184c-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="f184c-141">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f184c-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f184c-142">[Измерение задержки и проверка соединений для репликации транзакций](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f184c-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="f184c-143">[Мониторинг производительности с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f184c-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="f184c-144">[Наблюдение за репликацией](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f184c-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="f184c-145">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="f184c-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
