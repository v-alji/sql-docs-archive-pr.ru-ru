---
title: MSSQL_ENG014114 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654191"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="ce8c6-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="ce8c6-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ce8c6-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="ce8c6-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce8c6-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ce8c6-104">Product Name</span></span>|<span data-ttu-id="ce8c6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce8c6-105">SQL Server</span></span>|  
|<span data-ttu-id="ce8c6-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ce8c6-106">Event ID</span></span>|<span data-ttu-id="ce8c6-107">14114</span><span class="sxs-lookup"><span data-stu-id="ce8c6-107">14114</span></span>|  
|<span data-ttu-id="ce8c6-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ce8c6-108">Event Source</span></span>|<span data-ttu-id="ce8c6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ce8c6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ce8c6-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ce8c6-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ce8c6-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ce8c6-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ce8c6-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ce8c6-112">Message Text</span></span>|<span data-ttu-id="ce8c6-113">'%s' не настроен в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ce8c6-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ce8c6-114">Explanation</span></span>  
 <span data-ttu-id="ce8c6-115">Если в сообщении об ошибке указан конкретный экземпляр, отличный от NULL, это означает, что указанный экземпляр не был настроен должным образом для распознавания распространителем.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="ce8c6-116">Если в сообщении на месте распространителя указано значение NULL, это означает, что в **главной** базе данных нет записи для локального сервера или что эта запись неверна (например, если компьютер был переименован).</span><span class="sxs-lookup"><span data-stu-id="ce8c6-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="ce8c6-117">Репликация предполагает, что все серверы в топологии должны быть зарегистрированы с использованием имени компьютера и необязательного имени экземпляра (в случае кластеризованного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени виртуального сервера и необязательного имени экземпляра).</span><span class="sxs-lookup"><span data-stu-id="ce8c6-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="ce8c6-118">Для правильного функционирования репликации необходимо, чтобы значение, возвращаемое `SELECT @@SERVERNAME` для каждого сервера в топологии, соответствовало имени компьютера или имени виртуального сервера с необязательным именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="ce8c6-119">Репликация не поддерживается, если какой-либо из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зарегистрирован при помощи IP-адреса или полностью определенного имени домена (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ce8c6-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="ce8c6-120">Эта ошибка может возникать, если при настройке репликации любой из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] был зарегистрирован по IP-адресу или по FQDN в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce8c6-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce8c6-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ce8c6-121">User Action</span></span>  
 <span data-ttu-id="ce8c6-122">Если в ошибке указан конкретный экземпляр, необходимо настроить сервер в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="ce8c6-123">Дополнительные сведения см. в разделе [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="ce8c6-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="ce8c6-124">Если в сообщении не указан конкретный экземпляр (NULL), убедитесь, что экземпляр распространителя правильно зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="ce8c6-125">Если сетевое имя компьютера отличается от имени экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="ce8c6-126">Добавьте уникальное имя данного экземпляра SQL Server в качестве допустимого сетевого имени.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="ce8c6-127">Один из методов установки альтернативного сетевого имени — это добавление имени в локальный файл hosts.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="ce8c6-128">Локальный файл hosts по умолчанию расположен в каталоге WINDOWS\system32\drivers\etc или WINNT\system32\drivers\etc. Дополнительные сведения см. в документации Windows.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="ce8c6-129">Например, если имя компьютера — comp1, IP-адрес компьютера — 10.193.17.129, имя экземпляра — inst1/instname, то следует добавить в файл hosts следующую запись:</span><span class="sxs-lookup"><span data-stu-id="ce8c6-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="ce8c6-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="ce8c6-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="ce8c6-131">Отключите распространение, зарегистрируйте экземпляр и восстановите распространение.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="ce8c6-132">Если значение @@SERVERNAME недопустимо для некластеризованного экземпляра, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="ce8c6-133">После выполнения хранимой процедуры [sp_addserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) необходимо перезапустить службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы изменения параметра @@SERVERNAME вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="ce8c6-134">Если значение @@SERVERNAME недопустимо для кластеризованного экземпляра, необходимо изменить имя с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="ce8c6-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="ce8c6-135">Дополнительные сведения см. в статье [Экземпляры отказоустойчивого кластера (режим AlwaysOn) (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ce8c6-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8c6-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce8c6-136">See Also</span></span>  
 [<span data-ttu-id="ce8c6-137">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="ce8c6-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
