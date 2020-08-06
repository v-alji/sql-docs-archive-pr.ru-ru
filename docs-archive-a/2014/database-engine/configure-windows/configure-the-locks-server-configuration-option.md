---
title: Настройка параметра конфигурации сервера locks | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750147"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="1730b-102">Настройка параметра конфигурации сервера locks</span><span class="sxs-lookup"><span data-stu-id="1730b-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="1730b-103">В этом разделе описывается настройка параметра конфигурации сервера **locks** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1730b-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1730b-104">Параметр **locks** устанавливает максимальное число доступных блокировок, ограничивая таким образом объем памяти, используемый для них в компоненте [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1730b-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="1730b-105">Значение 0 (по умолчанию) позволяет компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] динамически выделять и освобождать структуры блокировок в зависимости от изменяющихся системных требований.</span><span class="sxs-lookup"><span data-stu-id="1730b-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="1730b-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1730b-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1730b-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1730b-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1730b-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1730b-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1730b-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1730b-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1730b-110">**Задание параметра locks с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="1730b-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="1730b-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1730b-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1730b-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1730b-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1730b-113">**Дальнейшие действия.**  [После настройки параметра locks](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1730b-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1730b-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1730b-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1730b-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1730b-115">Recommendations</span></span>  
  
-   <span data-ttu-id="1730b-116">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1730b-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="1730b-117">Когда сервер запускается с параметром **locks** , установленным в значение 0, диспетчер блокировок запрашивает у компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] объем памяти, достаточный для начального пула в 2500 структур блокировки.</span><span class="sxs-lookup"><span data-stu-id="1730b-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="1730b-118">Если пул блокировки будет исчерпан, для пула будет запрошена дополнительная память.</span><span class="sxs-lookup"><span data-stu-id="1730b-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="1730b-119">Вообще, если требуется больше памяти, чем доступно для пула блокировки в пуле памяти компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , и доступно больше компьютерной памяти (пороговое значение **максимальная память сервера** не было достигнуто), компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] динамически распределяет память, чтобы удовлетворить потребности запроса блокировок.</span><span class="sxs-lookup"><span data-stu-id="1730b-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="1730b-120">Однако, если распределение этой памяти вызовет подкачку страниц на уровне операционной системы (например, если другое приложение выполняется на том же самом компьютере как экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и использует эту память), большего объема пространства для блокировки не будет выделено.</span><span class="sxs-lookup"><span data-stu-id="1730b-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="1730b-121">Динамический пул блокировки не получит больше чем 60 процентов памяти, выделенной для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1730b-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="1730b-122">После того как пул блокировки достигнет 60 процентов памяти, запрошенной экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], или выяснится, что на компьютере нет больше доступной памяти, последующие запросы блокировок будут формировать ошибку.</span><span class="sxs-lookup"><span data-stu-id="1730b-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="1730b-123">Разрешение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использовать блокировки динамически является рекомендуемой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="1730b-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="1730b-124">Однако можно установить параметр **locks** и отключить динамическое распределение ресурсов блокировок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1730b-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="1730b-125">Когда параметр **locks** имеет значение, отличное от 0, [!INCLUDE[ssDE](../../includes/ssde-md.md)] не может распределить больше блокировок, чем указано в этом параметре **locks**.</span><span class="sxs-lookup"><span data-stu-id="1730b-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="1730b-126">Увеличьте это значение, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображает сообщение о том, что превышено количество доступных блокировок.</span><span class="sxs-lookup"><span data-stu-id="1730b-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="1730b-127">Так как каждая блокировка занимает память (96 байт на блокировку), увеличение этого значения может потребовать увеличения объема памяти, выделенной для сервера.</span><span class="sxs-lookup"><span data-stu-id="1730b-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="1730b-128">Параметр **locks** также оказывает влияние при укрупнении блокировки.</span><span class="sxs-lookup"><span data-stu-id="1730b-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="1730b-129">Когда параметр **locks** установлен в 0, укрупнение блокировки происходит тогда, когда память, используемая текущими структурами блокировки, достигает 40 процентов от пула памяти компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1730b-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="1730b-130">Если параметр **locks** установлен не в значение 0, укрупнение блокировки происходит, когда количество блокировок достигает 40 процентов от значения, указанного для параметра **locks**.</span><span class="sxs-lookup"><span data-stu-id="1730b-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1730b-131">безопасность</span><span class="sxs-lookup"><span data-stu-id="1730b-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1730b-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="1730b-132">Permissions</span></span>  
 <span data-ttu-id="1730b-133">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="1730b-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="1730b-134">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="1730b-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1730b-135">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1730b-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1730b-136">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1730b-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="1730b-137">Задание параметра locks</span><span class="sxs-lookup"><span data-stu-id="1730b-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="1730b-138">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1730b-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1730b-139">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="1730b-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="1730b-140">В разделе **Параллелизм**введите нужное значение параметра **locks** .</span><span class="sxs-lookup"><span data-stu-id="1730b-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="1730b-141">Используйте параметр **locks** для указания максимального числа доступных блокировок и, соответственно, для ограничения объема памяти, которую им выделяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1730b-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1730b-142">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1730b-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="1730b-143">Задание параметра locks</span><span class="sxs-lookup"><span data-stu-id="1730b-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="1730b-144">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1730b-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1730b-145">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1730b-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1730b-146">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1730b-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1730b-147">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для присвоения параметру `locks` значения, позволяющего установить число блокировок, доступных всем пользователям, равным `20000`.</span><span class="sxs-lookup"><span data-stu-id="1730b-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="1730b-148">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1730b-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a> <span data-ttu-id="1730b-149">Дальнейшие действия. После настройки параметра locks</span><span class="sxs-lookup"><span data-stu-id="1730b-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="1730b-150">Чтобы изменения вступили в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="1730b-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1730b-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="1730b-151">See Also</span></span>  
 <span data-ttu-id="1730b-152">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1730b-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1730b-153">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1730b-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="1730b-154">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1730b-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
