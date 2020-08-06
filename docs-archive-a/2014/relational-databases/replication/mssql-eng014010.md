---
title: MSSQL_ENG014010 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655075"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="1e385-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="1e385-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="1e385-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="1e385-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e385-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1e385-104">Product Name</span></span>|<span data-ttu-id="1e385-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1e385-105">SQL Server</span></span>|  
|<span data-ttu-id="1e385-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1e385-106">Event ID</span></span>|<span data-ttu-id="1e385-107">14010</span><span class="sxs-lookup"><span data-stu-id="1e385-107">14010</span></span>|  
|<span data-ttu-id="1e385-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1e385-108">Event Source</span></span>|<span data-ttu-id="1e385-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1e385-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1e385-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1e385-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="1e385-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1e385-111">Symbolic Name</span></span>||  
|<span data-ttu-id="1e385-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1e385-112">Message Text</span></span>|<span data-ttu-id="1e385-113">Сервер "%s" не определен как сервер подписок.</span><span class="sxs-lookup"><span data-stu-id="1e385-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e385-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1e385-114">Explanation</span></span>  
 <span data-ttu-id="1e385-115">Репликация предполагает, что все серверы в топологии должны быть зарегистрированы с использованием имени компьютера и необязательного имени экземпляра (в случае кластеризованного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени виртуального сервера и необязательного имени экземпляра).</span><span class="sxs-lookup"><span data-stu-id="1e385-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="1e385-116">Для правильного функционирования репликации необходимо, чтобы значение, возвращаемое `SELECT @@SERVERNAME` для каждого сервера в топологии, соответствовало имени компьютера или имени виртуального сервера с необязательным именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1e385-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="1e385-117">Репликация не поддерживается, если какой-либо из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зарегистрирован при помощи IP-адреса или полностью определенного имени домена (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1e385-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="1e385-118">Данная ошибка может возникнуть, если при настройке репликации имеются какие-либо экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , зарегистрированные с помощью IP-адреса или FQDN в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e385-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e385-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1e385-119">User Action</span></span>  
 <span data-ttu-id="1e385-120">Убедитесь в том, что все экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в топологии должным образом зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="1e385-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="1e385-121">Если сетевое имя компьютера отличается от имени экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1e385-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="1e385-122">Добавьте уникальное имя данного экземпляра SQL Server в качестве допустимого сетевого имени.</span><span class="sxs-lookup"><span data-stu-id="1e385-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="1e385-123">Один из методов установки альтернативного сетевого имени — это добавление имени в локальный файл hosts.</span><span class="sxs-lookup"><span data-stu-id="1e385-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="1e385-124">Локальный файл hosts по умолчанию расположен в каталоге WINDOWS\system32\drivers\etc или WINNT\system32\drivers\etc. Дополнительные сведения см. в документации Windows.</span><span class="sxs-lookup"><span data-stu-id="1e385-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="1e385-125">Например, если имя компьютера — comp1, IP-адрес компьютера — 10.193.17.129, имя экземпляра — inst1/instname, то следует добавить в файл hosts следующую запись:</span><span class="sxs-lookup"><span data-stu-id="1e385-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="1e385-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="1e385-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="1e385-127">Удалите репликацию, зарегистрируйте каждый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а затем восстановите репликацию.</span><span class="sxs-lookup"><span data-stu-id="1e385-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="1e385-128">Если значение @@SERVERNAME недопустимо для некластеризованного экземпляра, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1e385-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="1e385-129">После выполнения хранимой процедуры [sp_addserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) необходимо перезапустить службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы изменения параметра @@SERVERNAME вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="1e385-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="1e385-130">Если значение @@SERVERNAME недопустимо для кластеризованного экземпляра, необходимо изменить имя с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="1e385-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="1e385-131">Дополнительные сведения см. в разделе [Экземпляры отказоустойчивого кластера (режим AlwaysOn) (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e385-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e385-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e385-132">See Also</span></span>  
 <span data-ttu-id="1e385-133">[@@SERVERNAME (Transact-SQL)](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e385-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="1e385-134">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="1e385-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
