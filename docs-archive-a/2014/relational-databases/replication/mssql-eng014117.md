---
title: MSSQL_ENG014117 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654192"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="be6e2-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="be6e2-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="be6e2-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="be6e2-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be6e2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="be6e2-104">Product Name</span></span>|<span data-ttu-id="be6e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be6e2-105">SQL Server</span></span>|  
|<span data-ttu-id="be6e2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="be6e2-106">Event ID</span></span>|<span data-ttu-id="be6e2-107">14117</span><span class="sxs-lookup"><span data-stu-id="be6e2-107">14117</span></span>|  
|<span data-ttu-id="be6e2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="be6e2-108">Event Source</span></span>|<span data-ttu-id="be6e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="be6e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="be6e2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="be6e2-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="be6e2-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="be6e2-111">Symbolic Name</span></span>||  
|<span data-ttu-id="be6e2-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="be6e2-112">Message Text</span></span>|<span data-ttu-id="be6e2-113">"%s" не настроена в качестве базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="be6e2-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be6e2-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="be6e2-114">Explanation</span></span>  
 <span data-ttu-id="be6e2-115">Эта ошибка может произойти, если истинны одно или оба из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="be6e2-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="be6e2-116">Отсутствует в **msdb..MSdistributiondbs**вход для указанной базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="be6e2-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="be6e2-117">Отсутствует или некорректен вход для локального сервера в базу данных **master** .</span><span class="sxs-lookup"><span data-stu-id="be6e2-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="be6e2-118">Репликация предполагает, что все серверы в топологии должны быть зарегистрированы с использованием имени компьютера и необязательного имени экземпляра (в случае кластеризованного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени виртуального сервера и необязательного имени экземпляра).</span><span class="sxs-lookup"><span data-stu-id="be6e2-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="be6e2-119">Для правильного функционирования репликации необходимо, чтобы значение, возвращаемое `SELECT @@SERVERNAME` для каждого сервера в топологии, соответствовало имени компьютера или имени виртуального сервера с необязательным именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="be6e2-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="be6e2-120">Репликация не поддерживается, если какой-либо из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зарегистрирован при помощи IP-адреса или полностью определенного имени домена (FQDN).</span><span class="sxs-lookup"><span data-stu-id="be6e2-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="be6e2-121">Эта ошибка может возникать, если при настройке репликации любой из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] был зарегистрирован по IP-адресу или по FQDN в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be6e2-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be6e2-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="be6e2-122">User Action</span></span>  
 <span data-ttu-id="be6e2-123">Убедитесь, что экземпляр распространителя зарегистрирован правильно.</span><span class="sxs-lookup"><span data-stu-id="be6e2-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="be6e2-124">Если сетевое имя компьютера отличается от имени экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be6e2-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="be6e2-125">Добавьте уникальное имя данного экземпляра SQL Server в качестве допустимого сетевого имени.</span><span class="sxs-lookup"><span data-stu-id="be6e2-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="be6e2-126">Один из методов установки альтернативного сетевого имени — это добавление имени в локальный файл hosts.</span><span class="sxs-lookup"><span data-stu-id="be6e2-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="be6e2-127">Локальный файл hosts по умолчанию расположен в каталоге WINDOWS\system32\drivers\etc или WINNT\system32\drivers\etc. Дополнительные сведения см. в документации Windows.</span><span class="sxs-lookup"><span data-stu-id="be6e2-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="be6e2-128">Например, если имя компьютера — comp1, IP-адрес компьютера — 10.193.17.129, имя экземпляра — inst1/instname, то следует добавить в файл hosts следующую запись:</span><span class="sxs-lookup"><span data-stu-id="be6e2-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="be6e2-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="be6e2-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="be6e2-130">Отключите распространение, зарегистрируйте экземпляр и восстановите распространение.</span><span class="sxs-lookup"><span data-stu-id="be6e2-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="be6e2-131">Если значение @@SERVERNAME недопустимо для некластеризованного экземпляра, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be6e2-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="be6e2-132">После выполнения хранимой процедуры [sp_addserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) необходимо перезапустить службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы изменения параметра @@SERVERNAME вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="be6e2-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="be6e2-133">Если значение @@SERVERNAME недопустимо для кластеризованного экземпляра, необходимо изменить имя с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="be6e2-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="be6e2-134">Дополнительные сведения см. в статье [Экземпляры отказоустойчивого кластера (режим AlwaysOn) (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="be6e2-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="be6e2-135">После проверки верности регистрации экземпляра распространителя убедитесь в том, что база данных распространителя содержится в списке **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="be6e2-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="be6e2-136">Если базы данных в списке нет:</span><span class="sxs-lookup"><span data-stu-id="be6e2-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="be6e2-137">Создайте скрипт конфигурации распространения.</span><span class="sxs-lookup"><span data-stu-id="be6e2-137">Script out the distribution configuration.</span></span> <span data-ttu-id="be6e2-138">Дополнительные сведения см. в разделе [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="be6e2-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="be6e2-139">Отключите распространение, а затем включите его снова.</span><span class="sxs-lookup"><span data-stu-id="be6e2-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="be6e2-140">Дополнительные сведения см. в разделе [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="be6e2-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6e2-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="be6e2-141">See Also</span></span>  
 [<span data-ttu-id="be6e2-142">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="be6e2-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
