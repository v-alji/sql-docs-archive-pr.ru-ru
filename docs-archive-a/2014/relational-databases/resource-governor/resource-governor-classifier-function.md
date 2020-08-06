---
title: Функция-классификатор регулятора ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731466"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="86f82-102">Resource Governor Classifier Function</span><span class="sxs-lookup"><span data-stu-id="86f82-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="86f82-103">Процесс классификации регулятора ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] назначает входящие сеансы группе рабочей нагрузки с учетом характеристик сеанса.</span><span class="sxs-lookup"><span data-stu-id="86f82-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="86f82-104">Логику классификации можно адаптировать путем написания определяемой пользователем функции, называемой функцией-классификатором.</span><span class="sxs-lookup"><span data-stu-id="86f82-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="86f82-105">Классификация</span><span class="sxs-lookup"><span data-stu-id="86f82-105">Classification</span></span>  
 <span data-ttu-id="86f82-106">Регулятор ресурсов поддерживает классификацию входящих сеансов.</span><span class="sxs-lookup"><span data-stu-id="86f82-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="86f82-107">Классификация основывается на наборе пользовательских критериев, содержащихся в функции.</span><span class="sxs-lookup"><span data-stu-id="86f82-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="86f82-108">Результаты логики функции позволяют регулятору ресурсов классифицировать сеансы по существующим группам рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86f82-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86f82-109">Внутренняя группа рабочей нагрузки наполняется запросами, предназначенными только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="86f82-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="86f82-110">Критерии, используемые для перенаправления этих запросов, изменить нельзя, так же как нельзя классифицировать запросы во внутреннюю группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86f82-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="86f82-111">Можно написать скалярную функцию с логикой, которая будет использоваться для назначения входящих сеансов в группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86f82-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="86f82-112">Перед использованием этой функции необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="86f82-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="86f82-113">Создать и зарегистрировать функцию с помощью инструкции ALTER RESOURCE GOVERNOR.</span><span class="sxs-lookup"><span data-stu-id="86f82-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="86f82-114">Дополнительные сведения см. в разделе [ALTER RESOURCE GOVERNOR (Transact-SQL)](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86f82-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="86f82-115">Обновить конфигурацию регулятора ресурсов с помощью инструкции ALTER RESOURCE GOVERNOR с параметром RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="86f82-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="86f82-116">После создания функции и применения изменений в конфигурации классифицирующая функция регулятора ресурсов будет использовать возвращаемое этой функцией имя группы рабочей нагрузки для передачи нового запроса в соответствующую группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86f82-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86f82-117">Время ожидания клиентского сеанса истекает, если классифицирующая функция не завершается в течение заданного времени ожидания входа в систему.</span><span class="sxs-lookup"><span data-stu-id="86f82-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="86f82-118">Время ожидания входа в систему — это клиентское свойство, поэтому серверу оно неизвестно. Долго выполняемая функция-классификатор может оставлять на сервере потерянные соединения в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="86f82-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="86f82-119">Важно создавать функции-классификаторы, выполнение которых завершается до истечения времени ожидания соединения.</span><span class="sxs-lookup"><span data-stu-id="86f82-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="86f82-120">Определяемая пользователем функция имеет следующие характеристики и поведение.</span><span class="sxs-lookup"><span data-stu-id="86f82-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="86f82-121">Определяемая пользователем функция вычисляется для каждого нового сеанса, даже если включен пул соединений.</span><span class="sxs-lookup"><span data-stu-id="86f82-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="86f82-122">Определяемая пользователем функция предоставляет контекст группы рабочей нагрузки для сеанса.</span><span class="sxs-lookup"><span data-stu-id="86f82-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="86f82-123">После определения членства в группе сеанс привязывается к группе рабочей нагрузки на все время его существования.</span><span class="sxs-lookup"><span data-stu-id="86f82-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="86f82-124">Если определяемая пользователем функция возвращает значение NULL, значение по умолчанию или имя несуществующей группы, то сеансу предоставляется контекст группы рабочей нагрузки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86f82-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="86f82-125">Кроме того, сеансу предоставляется контекст по умолчанию, если функция по какой-либо причине завершается неуспешно.</span><span class="sxs-lookup"><span data-stu-id="86f82-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="86f82-126">Функция должна быть определена на уровне сервера (базы данных master).</span><span class="sxs-lookup"><span data-stu-id="86f82-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="86f82-127">Обозначение определяемой пользователем функции-классификатора вступает в силу только после выполнения команды ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="86f82-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="86f82-128">Одновременно в качестве классифицирующей функции может быть обозначена только одна определяемая пользователем функция.</span><span class="sxs-lookup"><span data-stu-id="86f82-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="86f82-129">Определяемую пользователем функцию-классификатор можно удалить или изменить только после снятия с нее статуса «classifier».</span><span class="sxs-lookup"><span data-stu-id="86f82-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="86f82-130">В отсутствие определяемой пользователем функции-классификатора все сеансы классифицируются в группу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86f82-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="86f82-131">Группа рабочей нагрузки, возвращенная классифицирующей функцией, выходит за пределы ограничений на привязку к схеме.</span><span class="sxs-lookup"><span data-stu-id="86f82-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="86f82-132">Например, нельзя удалить таблицу, тогда как группу рабочей нагрузки удалить можно.</span><span class="sxs-lookup"><span data-stu-id="86f82-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86f82-133">Рекомендуется включить на сервере выделенное административное соединение (DAC).</span><span class="sxs-lookup"><span data-stu-id="86f82-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="86f82-134">Выделенное административное соединение не подлежит классификации регулятором ресурсов и может использоваться для наблюдения за неполадками классифицирующей функции и их устранения.</span><span class="sxs-lookup"><span data-stu-id="86f82-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="86f82-135">Дополнительные сведения см. в разделе [Диагностическое соединение для администраторов баз данных](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="86f82-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="86f82-136">Если выделенное административное соединение недоступно для устранения неполадок, другой вариант — перезапустить систему в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="86f82-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="86f82-137">Хотя однопользовательский режим не подлежит классификации, он не дает возможности выполнить диагностику классификации регулятора ресурсов, если тот запущен.</span><span class="sxs-lookup"><span data-stu-id="86f82-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="86f82-138">Процесс классификации</span><span class="sxs-lookup"><span data-stu-id="86f82-138">Classification Process</span></span>  
 <span data-ttu-id="86f82-139">В контексте регулятора ресурсов процесс входа в сеанс состоит из следующих этапов.</span><span class="sxs-lookup"><span data-stu-id="86f82-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="86f82-140">Проверка подлинности имени входа.</span><span class="sxs-lookup"><span data-stu-id="86f82-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="86f82-141">Выполнение триггера LOGON.</span><span class="sxs-lookup"><span data-stu-id="86f82-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="86f82-142">Классификация</span><span class="sxs-lookup"><span data-stu-id="86f82-142">Classification</span></span>  
  
 <span data-ttu-id="86f82-143">После запуска сеанса классификатор регулятора ресурсов назначает этот сеанс группе рабочей нагрузки, и этот сеанс должен функционировать с использованием ресурсов, назначенных этой группе рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86f82-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86f82-144">Сведения о выполнении классифицирующей функции и триггеров LOGON содержатся в представлениях [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) и [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86f82-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="86f82-145">Задачи классифицирующей функции</span><span class="sxs-lookup"><span data-stu-id="86f82-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="86f82-146">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="86f82-146">Task Description</span></span>|<span data-ttu-id="86f82-147">Раздел</span><span class="sxs-lookup"><span data-stu-id="86f82-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="86f82-148">Описывает, как создать и проверить определяемую пользователем функцию-классификатор.</span><span class="sxs-lookup"><span data-stu-id="86f82-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="86f82-149">Создание и тестирование пользовательской функции-классификатора</span><span class="sxs-lookup"><span data-stu-id="86f82-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="86f82-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="86f82-150">See Also</span></span>  
 <span data-ttu-id="86f82-151">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="86f82-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="86f82-152">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="86f82-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="86f82-153">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="86f82-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="86f82-154">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="86f82-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="86f82-155">[Настройка регулятора ресурсов с помощью шаблона](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="86f82-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="86f82-156">Просмотр свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="86f82-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
