---
title: Общие свойства | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752396"
---
# <a name="general-properties"></a><span data-ttu-id="ea153-102">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="ea153-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ea153-103">поддерживают свойства сервера, перечисленные в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="ea153-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="ea153-104">В этом разделе описываются свойства сервера из файла msmdsrv.ini, которые не отнесены к тому или иному определенному разделу, например Security (безопасность), Network (сеть) или ThreadPool (пул потоков).</span><span class="sxs-lookup"><span data-stu-id="ea153-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="ea153-105">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea153-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="ea153-106">**Область применения:** многомерный или табличный режим сервера, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="ea153-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="ea153-107">Общая категория</span><span class="sxs-lookup"><span data-stu-id="ea153-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="ea153-108">Свойство с 32-разрядным целочисленным значением со знаком, определяющее время ожидания администратора (в секундах).</span><span class="sxs-lookup"><span data-stu-id="ea153-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="ea153-109">Это дополнительное свойство следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="ea153-110">Значение этого свойства по умолчанию равно нулю (0), то есть отсутствует время ожидания.</span><span class="sxs-lookup"><span data-stu-id="ea153-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="ea153-111">Строковое свойство, указывающее в списке с разделителями папки, которые можно просматривать при сохранении, открытии и нахождении файлов в диалоговых окнах служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ea153-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="ea153-112">Учетная запись служб Analysis Services должна иметь разрешения на чтение и запись на все добавленные в список папки.</span><span class="sxs-lookup"><span data-stu-id="ea153-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="ea153-113">Строковое свойство, определяющее имя каталога, в котором хранятся файлы резервных копий по умолчанию, в случае, если путь не указан как часть команды Backup.</span><span class="sxs-lookup"><span data-stu-id="ea153-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="ea153-114">Строковое свойство, определяющее параметры сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="ea153-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="ea153-115">Дополнительные сведения см. в разделе [Языки и параметры сортировки (службы Analysis Services)](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea153-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="ea153-116">Целочисленное свойство, указывающее время в миллисекундах, в течение которого сервер будет ожидать получения блокировки записи для фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="ea153-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="ea153-117">Период ожидания часто бывает необходим из-за того, что серверу приходится дожидаться снятия других блокировок, прежде чем он сможет установить блокировку записи, которая фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="ea153-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="ea153-118">Значение этого свойства по умолчанию равно нулю (0), то есть сервер ожидает бесконечно.</span><span class="sxs-lookup"><span data-stu-id="ea153-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="ea153-119">Дополнительные сведения о связанных с блокировкой свойствах см. в [руководстве по использованию служб SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ea153-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="ea153-120">Свойство с 32-разрядным целочисленным значением со знаком, определяющее максимальное количество потоков, назначенных для создания индексов секций.</span><span class="sxs-lookup"><span data-stu-id="ea153-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="ea153-121">Увеличьте это значение, чтобы ускорить индексацию секций за счет использования памяти.</span><span class="sxs-lookup"><span data-stu-id="ea153-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="ea153-122">Дополнительные сведения об этом свойстве см. в [Руководстве по использованию служб SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ea153-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="ea153-123">Свойство с 32-разрядным целочисленным значением со знаком, определяющее, как часто сервер должен проверять возникновение события Cancel (на основе внутреннего счетчика итераций).</span><span class="sxs-lookup"><span data-stu-id="ea153-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="ea153-124">Уменьшите это значение, чтобы чаще проверять событие Cancel за счет общей производительности.</span><span class="sxs-lookup"><span data-stu-id="ea153-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="ea153-125">Свойство `CoordinatorCancelCount` не учитывается в табличном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="ea153-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="ea153-126">Свойство с 32-разрядным целочисленным значением со знаком, определяющее максимальное количество параллельных операций, которые сервер пытается выполнить, включая обработку и запросы.</span><span class="sxs-lookup"><span data-stu-id="ea153-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="ea153-127">Ноль (0) указывает, что сервер принимает решение на основе внутреннего алгоритма.</span><span class="sxs-lookup"><span data-stu-id="ea153-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="ea153-128">Положительное число указывает общее количество операций.</span><span class="sxs-lookup"><span data-stu-id="ea153-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="ea153-129">Отрицательное число с обратным знаком указывает максимальное количество операций на процессор.</span><span class="sxs-lookup"><span data-stu-id="ea153-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="ea153-130">Свойство `CoordinatorExecutionMode` не учитывается в табличном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="ea153-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="ea153-131">Значение этого свойства по умолчанию равно -4, то есть сервер ограничен 4 параллельными операциями на процессор.</span><span class="sxs-lookup"><span data-stu-id="ea153-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="ea153-132">Дополнительные сведения об этом свойстве см. в [Руководстве по использованию служб SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ea153-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="ea153-133">Свойство с 32-разрядным целочисленным значением со знаком, определяющее максимальное число потоков на сегмент секции во время разрешения запроса.</span><span class="sxs-lookup"><span data-stu-id="ea153-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="ea153-134">Чем меньше число одновременных пользователей, тем выше может быть это значение за счет использования памяти.</span><span class="sxs-lookup"><span data-stu-id="ea153-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="ea153-135">И наоборот, это значение следует уменьшить при большом количестве одновременных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ea153-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="ea153-136">Логическое свойство, определяющее режим отключения координатора.</span><span class="sxs-lookup"><span data-stu-id="ea153-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="ea153-137">Это дополнительное свойство следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="ea153-138">Строковое свойство, определяющее имя папки, в которой хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="ea153-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="ea153-139">Определяет контекст работы экземпляра сервера служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ea153-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="ea153-140">Это свойство называется "режим сервера" в диалоговых окнах, сообщениях и документации.</span><span class="sxs-lookup"><span data-stu-id="ea153-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="ea153-141">Это свойство настраивается при установке SQL Server в соответствии с режимом сервера, выбранным при установке служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ea153-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="ea153-142">Это свойство следует рассматривать исключительно как внутреннее и всегда использовать в нем значение, указанное программой установки.</span><span class="sxs-lookup"><span data-stu-id="ea153-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="ea153-143">Ниже приведены допустимые значения для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="ea153-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="ea153-144">Значение</span><span class="sxs-lookup"><span data-stu-id="ea153-144">Value</span></span>|<span data-ttu-id="ea153-145">Описание</span><span class="sxs-lookup"><span data-stu-id="ea153-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea153-146">0</span><span class="sxs-lookup"><span data-stu-id="ea153-146">0</span></span>|<span data-ttu-id="ea153-147">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea153-147">This is the default value.</span></span> <span data-ttu-id="ea153-148">Оно задает многомерный режим, используемый для обслуживания многомерных баз данных с хранилищем MOLAP, HOLAP и ROLAP, а также с моделями интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ea153-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="ea153-149">1</span><span class="sxs-lookup"><span data-stu-id="ea153-149">1</span></span>|<span data-ttu-id="ea153-150">Указывает экземпляры служб Analysis Service, установленные в составе развертывания PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ea153-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="ea153-151">Не следует изменять свойство режима развертывания экземпляра служб Analysis Services, который входит в состав установки PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ea153-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="ea153-152">Если изменить режим, данные PowerPivot больше не будут выполняться на сервере.</span><span class="sxs-lookup"><span data-stu-id="ea153-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="ea153-153">2</span><span class="sxs-lookup"><span data-stu-id="ea153-153">2</span></span>|<span data-ttu-id="ea153-154">Задает табличный режим, используемый для размещения табличных шаблонов баз данных, использующих хранение в памяти или хранилище DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="ea153-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="ea153-155">Это монопольные режимы.</span><span class="sxs-lookup"><span data-stu-id="ea153-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="ea153-156">На сервере, где настроен табличный режим, не могут работать базы данных служб Analysis Services, содержащие кубы и измерения.</span><span class="sxs-lookup"><span data-stu-id="ea153-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="ea153-157">Если позволяет оборудование компьютера, можно установить на одном компьютере несколько экземпляров служб Analysis Services и настроить для каждого экземпляра свой режим развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea153-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="ea153-158">Следует помнить, что службы Analysis Services являются ресурсоемким приложением.</span><span class="sxs-lookup"><span data-stu-id="ea153-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="ea153-159">Развертывание нескольких экземпляров на одном компьютере рекомендуется только для мощных серверов.</span><span class="sxs-lookup"><span data-stu-id="ea153-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="ea153-160">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="ea153-161">Целочисленное свойство, определяющее время ожидания в секундах для команд, выданных внешним серверам, включая реляционные источники данных и внешние серверы служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="ea153-162">Значение данного свойства по умолчанию составляет 3600 (секунд).</span><span class="sxs-lookup"><span data-stu-id="ea153-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="ea153-163">Целочисленное свойство, определяющее время ожидания в секундах для создания соединений с внешними серверами, включая реляционные источники данных и внешние серверы служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="ea153-164">Это свойство не учитывается, если в строке подключения указано время ожидания соединения.</span><span class="sxs-lookup"><span data-stu-id="ea153-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="ea153-165">Значение данного свойства по умолчанию составляет 60 (секунд).</span><span class="sxs-lookup"><span data-stu-id="ea153-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="ea153-166">Целочисленное свойство, задающее время ожидания в миллисекундах для операции фиксации записи до отмены других команд, предшествующих текущей команде, в том числе выполняемым запросам.</span><span class="sxs-lookup"><span data-stu-id="ea153-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="ea153-167">Это обеспечивает выполнение фиксации транзакции за счет отмены таких операций с более низким приоритетом, как запросы.</span><span class="sxs-lookup"><span data-stu-id="ea153-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="ea153-168">Значение этого свойства по умолчанию равно 30 секундам (30 000 миллисекундам), то есть другие команды не используют время ожидания, пока время ожидания фиксации транзакции не достигнет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="ea153-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea153-169">Запросы и процессы, отмененные этим событием, будут выдавать следующее сообщение об ошибке: "`Server: The operation has been cancelled`".</span><span class="sxs-lookup"><span data-stu-id="ea153-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="ea153-170">Дополнительные сведения об этом свойстве см. в [Руководстве по использованию служб SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ea153-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea153-171">`ForceCommitTimeout` применяется к командам обработки куба и операциям обратной записи.</span><span class="sxs-lookup"><span data-stu-id="ea153-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="ea153-172">Целочисленное свойство, задающее время ожидания в секундах для неактивных соединений.</span><span class="sxs-lookup"><span data-stu-id="ea153-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="ea153-173">Значение этого свойства по умолчанию равно нулю (0), то есть время ожидания соединения не используется.</span><span class="sxs-lookup"><span data-stu-id="ea153-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="ea153-174">Целочисленное свойство определяющее время в секундах для хранения потерянных сеансов в памяти.</span><span class="sxs-lookup"><span data-stu-id="ea153-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="ea153-175">Потерянный сеанс — это сеанс, с которым не связано соединение.</span><span class="sxs-lookup"><span data-stu-id="ea153-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="ea153-176">Значение по умолчанию — 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="ea153-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="ea153-177">Логическое свойство, указывающее, является ли экземпляр сервера видимым для запросов к экземпляру от службы обозревателя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea153-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="ea153-178">Значение по умолчанию равно True.</span><span class="sxs-lookup"><span data-stu-id="ea153-178">The default is True.</span></span> <span data-ttu-id="ea153-179">Если присвоить ему значение false, то экземпляр будет невидим для обозревателя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea153-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="ea153-180">Строковое свойство, определяющее язык, включая сообщения об ошибках и форматирование чисел.</span><span class="sxs-lookup"><span data-stu-id="ea153-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="ea153-181">Это свойство переопределяет свойство CollationName.</span><span class="sxs-lookup"><span data-stu-id="ea153-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="ea153-182">Значение этого свойства по умолчанию отсутствует, то есть язык определяется свойством CollationName.</span><span class="sxs-lookup"><span data-stu-id="ea153-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="ea153-183">Строковое свойство, определяющее имя папки, в которой хранятся журналы сервера.</span><span class="sxs-lookup"><span data-stu-id="ea153-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="ea153-184">Данное свойство применяется только тогда, когда для ведения журнала используются дисковые файлы, а не таблицы баз данных (настройка по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ea153-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="ea153-185">Целочисленное свойство, определяющее максимальное время ожидания в секундах для бездействующего сеанса.</span><span class="sxs-lookup"><span data-stu-id="ea153-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="ea153-186">Значение по умолчанию равно нулю (0), что означает, что сеансы никогда не превышены. Однако бездействующие сеансы по-прежнему будут удалены, если сервер находится под ограничениями ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ea153-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="ea153-187">Целочисленное свойство, определяющее минимальное время ожидания для бездействующего сеанса (в секундах).</span><span class="sxs-lookup"><span data-stu-id="ea153-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="ea153-188">Значение по умолчанию — 2700 секунд.</span><span class="sxs-lookup"><span data-stu-id="ea153-188">The default is 2700 seconds.</span></span> <span data-ttu-id="ea153-189">После истечения этого времени серверу разрешается закончить сеанс простоя, но только если требуется память.</span><span class="sxs-lookup"><span data-stu-id="ea153-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="ea153-190">Целочисленное свойство, определяющее номер порта, на котором сервер прослушивает соединения клиентов.</span><span class="sxs-lookup"><span data-stu-id="ea153-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="ea153-191">Если это свойство не задано, то сервер динамически находит первый неиспользуемый порт.</span><span class="sxs-lookup"><span data-stu-id="ea153-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="ea153-192">Значение этого свойства по умолчанию равно нулю (0), то есть по умолчанию используется порт 2383.</span><span class="sxs-lookup"><span data-stu-id="ea153-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="ea153-193">Дополнительные сведения о настройке порта см. в разделе [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="ea153-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="ea153-194">Целое число, определяющее время ожидания в секундах для запросов.</span><span class="sxs-lookup"><span data-stu-id="ea153-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="ea153-195">Значение по умолчанию равно 3600 секундам (или 60 минутам).</span><span class="sxs-lookup"><span data-stu-id="ea153-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="ea153-196">Нуль (0) означает, что время ожидания запросов не истекает.</span><span class="sxs-lookup"><span data-stu-id="ea153-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="ea153-197">Строковое свойство, задающее расположение для сохранения временных файлов во время обработки, восстановления и других действий.</span><span class="sxs-lookup"><span data-stu-id="ea153-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="ea153-198">Значение этого свойства по умолчанию определяется настройкой.</span><span class="sxs-lookup"><span data-stu-id="ea153-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="ea153-199">Если свойство не задано, то по умолчанию используется папка Data.</span><span class="sxs-lookup"><span data-stu-id="ea153-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="ea153-200">Категория RequestPrioritization</span><span class="sxs-lookup"><span data-stu-id="ea153-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="ea153-201">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="ea153-202">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea153-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea153-203">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea153-203">See Also</span></span>  
 <span data-ttu-id="ea153-204">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ea153-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="ea153-205">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ea153-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
