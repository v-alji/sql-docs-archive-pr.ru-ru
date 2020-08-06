---
title: Изменение целевого времени восстановления базы данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658260"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="2858a-102">Изменение целевого времени восстановления базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2858a-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="2858a-103">В этом разделе описывается изменение целевого времени восстановления базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2858a-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2858a-104">По умолчанию целевое время восстановления — 0, а база данных использует *автоматические контрольные точки* , задаваемые при помощи параметра сервера **интервал восстановления** .</span><span class="sxs-lookup"><span data-stu-id="2858a-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="2858a-105">Установка значения времени восстановления &gt; 0 ведет к тому, что база данных будет использовать *непрямые контрольные точки* и установит верхнюю границу времени восстановления для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="2858a-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2858a-106">Верхняя граница, указываемая для отдельной базы данных посредством настройки целевого времени восстановления, может быть превышена из-за долгой транзакции, которая может вызвать чрезмерное время для отмены действий.</span><span class="sxs-lookup"><span data-stu-id="2858a-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="2858a-107">**Перед началом работы**  [Ограничения](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="2858a-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="2858a-108">**Изменение целевого времени восстановления с помощью**   [SQL Server Management Studio](#SSMSProcedure) или [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="2858a-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2858a-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2858a-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="2858a-110">В базе данных, которая настроена на использование косвенных контрольных точек, может снизиться производительность обработки транзакционной нагрузки в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="2858a-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="2858a-111">Косвенные конечные точки сохраняют количество «грязных» страниц ниже определенного порогового значения, чтобы восстановление базы данных выполнялось в течение заданного времени восстановления.</span><span class="sxs-lookup"><span data-stu-id="2858a-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="2858a-112">Параметр конфигурации интервала восстановления использует количество транзакций для определения времени восстановления вместо косвенных конечных точек, которые основываются на количестве «грязных» страниц.</span><span class="sxs-lookup"><span data-stu-id="2858a-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="2858a-113">Если косвенные конечные точки включены в базе данных, получающей большое число операций DML, средство фоновой записи может начать агрессивно сбрасывать «грязные» буферы обмена на диск, чтобы гарантировать, что время, необходимое для выполнения восстановления, находится в пределах целевого периода восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="2858a-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="2858a-114">Это может вызвать дополнительную активность операций ввода-вывода в определенных системах, что способно привести к созданию узких мест с точки зрения производительности, если подсистема диска превысила пороговое значение операций ввода-вывода или приближается к нему.</span><span class="sxs-lookup"><span data-stu-id="2858a-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2858a-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="2858a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2858a-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="2858a-116">Permissions</span></span>  
 <span data-ttu-id="2858a-117">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="2858a-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2858a-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2858a-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2858a-119">**Изменение целевого времени восстановления**</span><span class="sxs-lookup"><span data-stu-id="2858a-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="2858a-120">В **обозревателе объектов**подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="2858a-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="2858a-121">Щелкните правой кнопкой мыши базу данных, которую необходимо изменить, и выберите команду **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="2858a-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="2858a-122">В диалоговом окне **Свойства базы данных** выберите страницу **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="2858a-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="2858a-123">На панели **Восстановление** в поле **Целевое время восстановления (секунды)** укажите количество секунд в качестве верхней границы времени восстановления этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="2858a-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2858a-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2858a-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="2858a-125">**Изменение целевого времени восстановления**</span><span class="sxs-lookup"><span data-stu-id="2858a-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="2858a-126">Установите подключение к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором размещена база данных.</span><span class="sxs-lookup"><span data-stu-id="2858a-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="2858a-127">Используйте инструкцию [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2858a-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="2858a-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="2858a-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="2858a-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="2858a-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="2858a-130">Если значение &gt; 0 (0 — значение по умолчанию), то оно указывает значение верхней границы времени восстановления для заданной базы данных в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="2858a-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="2858a-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="2858a-131">SECONDS</span></span>  
     <span data-ttu-id="2858a-132">Указывает, что значение *target_recovery_time* выражается в количестве секунд.</span><span class="sxs-lookup"><span data-stu-id="2858a-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="2858a-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="2858a-133">MINUTES</span></span>  
     <span data-ttu-id="2858a-134">Указывает, что значение *target_recovery_time* выражается в количестве минут.</span><span class="sxs-lookup"><span data-stu-id="2858a-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="2858a-135">В следующем примере устанавливается время восстановления базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] в `60` секунд.</span><span class="sxs-lookup"><span data-stu-id="2858a-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2858a-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="2858a-136">See Also</span></span>  
 <span data-ttu-id="2858a-137">[Контрольные точки базы данных (SQL Server)](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2858a-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="2858a-138">Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2858a-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
