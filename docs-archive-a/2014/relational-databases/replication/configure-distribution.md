---
title: Настройка распространения | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], distribution
- distribution configuration [SQL Server replication]
- remote Distributors [SQL Server replication]
- transactional replication, configuring distribution
- distribution databases [SQL Server replication], sizing
- Distributors [SQL Server replication], configuring
- distribution databases [SQL Server replication], about distribution databases
- distribution databases [SQL Server replication]
- merge replication [SQL Server replication], configuring distribution
ms.assetid: 94d52169-384e-4885-84eb-2304e967d9f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0378fe285ba57e1420b7e6bebf5e2e6fe13d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657657"
---
# <a name="configure-distribution"></a><span data-ttu-id="464e8-102">Настройка распространителя</span><span class="sxs-lookup"><span data-stu-id="464e8-102">Configure Distribution</span></span>
  <span data-ttu-id="464e8-103">Распространитель — это сервер, на котором находится база данных распространителя, хранящая метаданные и данные предыстории для всех типов репликации, а также транзакции репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="464e8-103">The Distributor is a server that contains the distribution database, which stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="464e8-104">Для настройки репликации, необходимо настроить распространитель.</span><span class="sxs-lookup"><span data-stu-id="464e8-104">To set up replication, you must configure a Distributor.</span></span> <span data-ttu-id="464e8-105">Каждый издатель может быть назначен только одному экземпляру распространителя, однако один распространитель может совместно использоваться несколькими издателями.</span><span class="sxs-lookup"><span data-stu-id="464e8-105">Each Publisher can be assigned to only a single Distributor instance, but multiple publishers can share a Distributor.</span></span> <span data-ttu-id="464e8-106">Распространитель использует следующие дополнительные ресурсы на сервере, где он расположен.</span><span class="sxs-lookup"><span data-stu-id="464e8-106">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="464e8-107">Дополнительное дисковое пространство, если файлы моментальных снимков для публикации хранятся на распространителе (где они обычно и хранятся).</span><span class="sxs-lookup"><span data-stu-id="464e8-107">Additional disk space if the snapshot files for the publication are stored on the Distributor (which they typically are).</span></span>  
  
-   <span data-ttu-id="464e8-108">Дополнительное место на диске для хранения базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="464e8-108">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="464e8-109">Дополнительное использование процессора агентами репликации для принудительных подписок на распространителе.</span><span class="sxs-lookup"><span data-stu-id="464e8-109">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="464e8-110">Сервер, который был выбран в качестве распространителя, должен иметь достаточно места на диске и достаточно мощный процессор для поддержки репликации и других действий на данном сервере.</span><span class="sxs-lookup"><span data-stu-id="464e8-110">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span> <span data-ttu-id="464e8-111">При настройке распространителя указываются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="464e8-111">When you configure the Distributor, you specify the following:</span></span>  
  
-   <span data-ttu-id="464e8-112">Папку моментальных снимков, применяемую по умолчанию для всех издателей, которые используют этот распространитель.</span><span class="sxs-lookup"><span data-stu-id="464e8-112">A snapshot folder, which is used, by default, for all Publishers that use this Distributor.</span></span> <span data-ttu-id="464e8-113">Убедитесь, что эта папка уже открыта для общего доступа и имеет соответствующий набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="464e8-113">Ensure that this folder is already shared and has the appropriate permissions set.</span></span> <span data-ttu-id="464e8-114">Дополнительные сведения см. в статье [Организация безопасности папки моментальных снимков](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="464e8-114">For more information, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  
-   <span data-ttu-id="464e8-115">Имя и расположение файлов базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="464e8-115">A name and file locations for the distribution database.</span></span> <span data-ttu-id="464e8-116">База данных распространителя не может быть переименована после создания.</span><span class="sxs-lookup"><span data-stu-id="464e8-116">The distribution database cannot be renamed after it is created.</span></span> <span data-ttu-id="464e8-117">Для использования иного имени для базы данных необходимо отключить распространение и установить конфигурацию заново.</span><span class="sxs-lookup"><span data-stu-id="464e8-117">To use a different name for the database, you must disable distribution and reconfigure it.</span></span>  
  
-   <span data-ttu-id="464e8-118">Любые издатели, наделенные правами использования распространителя.</span><span class="sxs-lookup"><span data-stu-id="464e8-118">Any Publishers authorized to use the Distributor.</span></span> <span data-ttu-id="464e8-119">Если указываются издатели, отличные от экземпляра, на котором выполняется распространитель, необходимо также указать пароль для установки подключений издателей к удаленному распространителю.</span><span class="sxs-lookup"><span data-stu-id="464e8-119">If you specify Publishers other than the instance on which the Distributor runs, you must also specify a password for the connections the Publishers make to the remote Distributor.</span></span>  
  
 <span data-ttu-id="464e8-120">Для репликации транзакций, после настройки распространения рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="464e8-120">For transactional replication, after you configure distribution, we recommend that you:</span></span>  
  
-   <span data-ttu-id="464e8-121">Установите надлежащий размер для базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="464e8-121">Size the distribution database appropriately.</span></span> <span data-ttu-id="464e8-122">Проверьте репликацию с типовой нагрузкой системы, чтобы определить пространство, необходимое для хранения команд.</span><span class="sxs-lookup"><span data-stu-id="464e8-122">Test replication with a typical load for your system to determine how much space is required to store commands.</span></span> <span data-ttu-id="464e8-123">Убедитесь в том, что база данных имеет достаточный размер для хранения команд без частого автоматического увеличения размера.</span><span class="sxs-lookup"><span data-stu-id="464e8-123">Ensure the database is large enough to store commands without having to auto-grow frequently.</span></span> <span data-ttu-id="464e8-124">Дополнительные сведения об изменении размера базы данных см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="464e8-124">For more information about changing the size of a database, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="464e8-125">Установите параметр **sync with backup** для базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="464e8-125">Set the **sync with backup** option on the distribution database.</span></span> <span data-ttu-id="464e8-126">Дополнительные сведения см. в статье [Стратегии резервного копирования и восстановления из копии репликации моментальных снимков и репликации транзакций](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) и [Включение скоординированного резервного копирования для репликации транзакций (программирование репликации на языке Transact-SQL)](administration/enable-coordinated-backups-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="464e8-126">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) and [Enable Coordinated Backups for Transactional Replication &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span></span>  
  
## <a name="local-and-remote-distributors"></a><span data-ttu-id="464e8-127">Локальный и удаленный распространители</span><span class="sxs-lookup"><span data-stu-id="464e8-127">Local and Remote Distributors</span></span>  
 <span data-ttu-id="464e8-128">По умолчанию распространитель является тем же самым сервером, что и издатель (локальный распространитель), но он может быть также и отдельным сервером, отличным от сервера издателя (удаленный распространитель).</span><span class="sxs-lookup"><span data-stu-id="464e8-128">By default, the Distributor is the same server as the Publisher (a local Distributor), but it can also be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="464e8-129">Обычно удаленный распространитель используется в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="464e8-129">Typically, you would choose to use a remote Distributor if you want to:</span></span>  
  
-   <span data-ttu-id="464e8-130">Перенос обработки на другой компьютер, если требуется минимизировать влияние репликации на издатель (например, если издатель является сервером интерактивной обработки транзакций (OLTP)).</span><span class="sxs-lookup"><span data-stu-id="464e8-130">Offload processing to another computer if you want minimal impact from replication on the Publisher (for example, if the Publisher is an OLTP server).</span></span>  
  
-   <span data-ttu-id="464e8-131">Настройка централизованного распространителя для нескольких издателей.</span><span class="sxs-lookup"><span data-stu-id="464e8-131">Configure a centralized Distributor for multiple Publishers.</span></span>  
  
 <span data-ttu-id="464e8-132">Удаленные распространители чаще используются в репликации транзакций, чем в репликации слиянием по двум причинам:</span><span class="sxs-lookup"><span data-stu-id="464e8-132">Remote Distributors are more common in transactional replication than they are in merge replication for two reasons:</span></span>  
  
-   <span data-ttu-id="464e8-133">Распространитель играет большую роль в репликации транзакций, так как все реплицированные транзакции записываются в базу данных распространителя и считываются из нее.</span><span class="sxs-lookup"><span data-stu-id="464e8-133">The Distributor plays a larger role in transactional replication because all replicated transactions are written to and read from the distribution database.</span></span>  
  
-   <span data-ttu-id="464e8-134">В топологиях репликации слиянием обычно используются подписки по запросу, так что все агенты выполняются на каждом подписчике вместо выполнения на распространителе.</span><span class="sxs-lookup"><span data-stu-id="464e8-134">Merge replication topologies typically use pull subscriptions, so agents run at each Subscriber, rather than all running at the Distributor.</span></span> <span data-ttu-id="464e8-135">Дополнительные сведения см. в статье [Подписка на публикации](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="464e8-135">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="464e8-136">В большинстве случаев для репликации слиянием необходимо использовать локальный распространитель.</span><span class="sxs-lookup"><span data-stu-id="464e8-136">In most cases, you should use a local Distributor for merge replication.</span></span>  
  
 <span data-ttu-id="464e8-137">Чтобы настроить публикацию и распространение, см. раздел [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="464e8-137">To configure publishing and distribution, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  
  
 <span data-ttu-id="464e8-138">Чтобы изменить свойства издателя и распространителя, см. раздел [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="464e8-138">To modify Publisher and Distributor properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464e8-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="464e8-139">See Also</span></span>  
 <span data-ttu-id="464e8-140">[Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="464e8-140">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="464e8-141">Защита распространителя</span><span class="sxs-lookup"><span data-stu-id="464e8-141">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
