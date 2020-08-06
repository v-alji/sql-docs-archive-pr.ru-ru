---
title: MSSQLSERVER_30053 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 8ad23889-e243-4bd7-bc3e-150403399d89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 02d6262f93ef3dbbc9834053f864046b4dca30f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664255"
---
# <a name="mssqlserver_30053"></a><span data-ttu-id="07d02-102">MSSQLSERVER_30053</span><span class="sxs-lookup"><span data-stu-id="07d02-102">MSSQLSERVER_30053</span></span>
    
## <a name="details"></a><span data-ttu-id="07d02-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="07d02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07d02-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="07d02-104">Product Name</span></span>|<span data-ttu-id="07d02-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="07d02-105">SQL Server</span></span>|  
|<span data-ttu-id="07d02-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="07d02-106">Event ID</span></span>|<span data-ttu-id="07d02-107">30053</span><span class="sxs-lookup"><span data-stu-id="07d02-107">30053</span></span>|  
|<span data-ttu-id="07d02-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="07d02-108">Event Source</span></span>|<span data-ttu-id="07d02-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="07d02-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="07d02-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="07d02-110">Component</span></span>|<span data-ttu-id="07d02-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="07d02-111">SQLEngine</span></span>|  
|<span data-ttu-id="07d02-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="07d02-112">Symbolic Name</span></span>|<span data-ttu-id="07d02-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07d02-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span></span>|  
|<span data-ttu-id="07d02-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="07d02-114">Message Text</span></span>|<span data-ttu-id="07d02-115">Истекло время ожидания при выполнении разбиения по словам для строки полнотекстового запроса.</span><span class="sxs-lookup"><span data-stu-id="07d02-115">Word breaking timed out for the full-text query string.</span></span> <span data-ttu-id="07d02-116">Это может произойти в том случае, если средство разбиения по словам слишком долго обрабатывало строку полнотекстового запроса либо если на сервере одновременно выполняется большое количество запросов.</span><span class="sxs-lookup"><span data-stu-id="07d02-116">This can happen if the wordbreaker took a long time to process the full-text query string, or if a large number of queries are running on the server.</span></span> <span data-ttu-id="07d02-117">Попробуйте выполнить запрос еще раз при меньшей загрузке сервера.</span><span class="sxs-lookup"><span data-stu-id="07d02-117">Try running the query again under a lighter load.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07d02-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="07d02-118">Explanation</span></span>  
 <span data-ttu-id="07d02-119">Ошибка времени ожидания при разбиении по словам может случаться в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="07d02-119">A word-breaking timeout error can occur in the following situations:</span></span>  
  
-   <span data-ttu-id="07d02-120">Неправильно настроено средство разбиения по словам для языка запроса. Например, для него неправильно заданы параметры в реестре.</span><span class="sxs-lookup"><span data-stu-id="07d02-120">The word breaker for the query language is configured incorrectly; for example, its registry settings are incorrect.</span></span>  
  
-   <span data-ttu-id="07d02-121">Средство разбиения по словам неправильно обрабатывает определенную строку запроса.</span><span class="sxs-lookup"><span data-stu-id="07d02-121">The word breaker malfunctions for a specific query string.</span></span>  
  
-   <span data-ttu-id="07d02-122">Средство разбиения по словам возвращает слишком много данных для определенной строки запроса.</span><span class="sxs-lookup"><span data-stu-id="07d02-122">The word breaker returns too much data for a specific query string.</span></span> <span data-ttu-id="07d02-123">Избыток данных воспринимается как потенциальная ошибка переполнения буфера, и процесс управляющей программы фильтрации (fdhost.exe), который выполняет службы разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="07d02-123">Excess data is treated as a potential buffer overrun attack, and shuts down the filter daemon process (fdhost.exe), which hosts the word-breaking services.</span></span>  
  
-   <span data-ttu-id="07d02-124">Неправильная конфигурация процесса управляющей программы фильтрации.</span><span class="sxs-lookup"><span data-stu-id="07d02-124">The filter daemon process configuration is incorrect.</span></span>  
  
     <span data-ttu-id="07d02-125">Типичные ошибки конфигурации: истек срок действия пароля или задействована политика домена, которая запрещает вход для учетной записи управляющей программы фильтрации.</span><span class="sxs-lookup"><span data-stu-id="07d02-125">The most common configuration problems are password expiration or a domain policy that prevents the filter daemon account from logging on.</span></span>  
  
-   <span data-ttu-id="07d02-126">В экземпляре сервера обрабатывается чрезвычайно высокий объем нагрузки со стороны запросов. Например, средству разбиения по словам потребовалось продолжительное время для обработки строки полнотекстового запроса или на сервере выполняется большое количество запросов.</span><span class="sxs-lookup"><span data-stu-id="07d02-126">A very heavy query workload is running on the server instance; for example, the word-breaker took a long time to process the full-text query string, or a large number of queries are running on the server.</span></span> <span data-ttu-id="07d02-127">Заметьте, что это наименее вероятная причина.</span><span class="sxs-lookup"><span data-stu-id="07d02-127">Note that this is the least likely cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07d02-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="07d02-128">User Action</span></span>  
 <span data-ttu-id="07d02-129">Выберите по следующей таблице действие пользователя, подходящее для устранения предполагаемой причины превышения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="07d02-129">Select the user action that is appropriate to the probable cause of the timeout, as follows:</span></span>  
  
|<span data-ttu-id="07d02-130">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="07d02-130">Probable cause</span></span>|<span data-ttu-id="07d02-131">Рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="07d02-131">User action</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="07d02-132">Неправильно настроено средство разбиения по словам для языка запросов.</span><span class="sxs-lookup"><span data-stu-id="07d02-132">The word breaker for the query language is configured incorrectly.</span></span>|<span data-ttu-id="07d02-133">Если используется средство разбиения по словам сторонних разработчиков, оно может быть неправильно зарегистрировано в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="07d02-133">If you are using a third-party word breaker it might be incorrectly registered with the operating system.</span></span> <span data-ttu-id="07d02-134">В этом случае повторно зарегистрируйте средство разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="07d02-134">In this case, re-register the word breaker.</span></span> <span data-ttu-id="07d02-135">Дополнительные сведения см. в статье [Восстановление предыдущих версий средств разбиения текста на слова, используемых поиском](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span><span class="sxs-lookup"><span data-stu-id="07d02-135">For more information, see [Revert the Word Breakers Used by Search to the Previous Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span></span>|  
|<span data-ttu-id="07d02-136">Средство разбиения по словам неправильно обрабатывает определенную строку запроса.</span><span class="sxs-lookup"><span data-stu-id="07d02-136">The word breaker malfunctions for a specific query string.</span></span>|<span data-ttu-id="07d02-137">Если средство разбиения по словам поддерживается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], обратитесь в службу поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07d02-137">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="07d02-138">Средство разбиения по словам возвращает слишком много данных для определенной строки запроса.</span><span class="sxs-lookup"><span data-stu-id="07d02-138">The word breaker returns too much data for a specific query string.</span></span>|<span data-ttu-id="07d02-139">Если средство разбиения по словам поддерживается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], обратитесь в службу поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="07d02-139">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="07d02-140">Неправильная конфигурация процесса управляющей программы фильтрации.</span><span class="sxs-lookup"><span data-stu-id="07d02-140">The filter daemon process configuration is incorrect.</span></span>|<span data-ttu-id="07d02-141">Убедитесь, что используется текущий пароль, а политика домена не запрещает вход для учетной записи управляющей программы фильтрации.</span><span class="sxs-lookup"><span data-stu-id="07d02-141">Ensure that you are using the current password and that a domain policy is not preventing the filter daemon account from logging on.</span></span>|  
|<span data-ttu-id="07d02-142">В экземпляре сервера обрабатывается рабочая нагрузка запросов очень большого объема.</span><span class="sxs-lookup"><span data-stu-id="07d02-142">A very heavy query workload is running on the server instance.</span></span>|<span data-ttu-id="07d02-143">Попробуйте выполнить запрос еще раз при меньшей загрузке сервера.</span><span class="sxs-lookup"><span data-stu-id="07d02-143">Try running the query again under a lighter load.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07d02-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="07d02-144">See Also</span></span>  
 <span data-ttu-id="07d02-145">[Настройка учетной записи службы для средства запуска управляющей программы полнотекстовой фильтрации](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="07d02-145">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="07d02-146">[Компонент Full-text Search](../search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="07d02-146">[Full-Text Search](../search/full-text-search.md) </span></span>  
 <span data-ttu-id="07d02-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="07d02-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="07d02-148">[Настройка средств разбиения по словам и парадигматические модули для поиска и управление ими](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="07d02-148">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="07d02-149">Настройка и управление фильтрами для поиска</span><span class="sxs-lookup"><span data-stu-id="07d02-149">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
