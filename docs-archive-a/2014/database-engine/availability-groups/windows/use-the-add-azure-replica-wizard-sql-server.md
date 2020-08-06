---
title: Использование мастера добавления реплики Azure (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728701"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="02166-102">Использование мастера добавления реплики Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="02166-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="02166-103">С помощью мастера добавления реплики Azure вы сможете создать виртуальную машину Azure в гибридной ИТ-службе и настроить ее в качестве вторичной реплики для новой или существующей группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="02166-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="02166-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="02166-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02166-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="02166-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="02166-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="02166-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02166-107">**Для добавления реплики воспользуйтесь инструкциями из раздела**  [Мастер добавления реплики Azure (среда SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="02166-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02166-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="02166-108">Before You Begin</span></span>  
 <span data-ttu-id="02166-109">Если вы еще не добавили реплику доступности в группу доступности, см. разделы "экземпляры сервера" и "группы доступности и реплики" в разделе [Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="02166-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="02166-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="02166-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="02166-111">Необходимо подключиться к экземпляру сервера, на котором размещена текущая первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="02166-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="02166-112">Необходима гибридная среда, где в локальной подсети установлено VPN-подключение типа "сеть — сеть" к Azure.</span><span class="sxs-lookup"><span data-stu-id="02166-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="02166-113">Дополнительные сведения см. в разделе [Настройка виртуальной частной сети между площадками через портал управления](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="02166-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="02166-114">Группа доступности должна содержать реплики доступности локально.</span><span class="sxs-lookup"><span data-stu-id="02166-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="02166-115">Клиенты прослушивателя группы доступности должны быть подключены к Интернету, если им нужно поддерживать соединение с прослушивателем при выполнении отработки отказа группы доступности в реплику Azure.</span><span class="sxs-lookup"><span data-stu-id="02166-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="02166-116">**Предварительные условия для использования полной начальной синхронизации данных** Необходимо указать сетевой ресурс, чтобы мастер мог создавать и получать доступ к резервным копиям.</span><span class="sxs-lookup"><span data-stu-id="02166-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="02166-117">Для каждой первичной реплики учетная запись, используемая для запуска [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , должна иметь разрешения в файловой системе на чтение и запись в общей сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="02166-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="02166-118">Для вторичных реплик учетная запись должна иметь разрешение на чтение в сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="02166-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="02166-119">Если нет возможности воспользоваться мастером для выполнения полной первоначальной синхронизации данных, то базы данных-получатели нужно подготовить вручную.</span><span class="sxs-lookup"><span data-stu-id="02166-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="02166-120">Это можно сделать до или после запуска мастера.</span><span class="sxs-lookup"><span data-stu-id="02166-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="02166-121">Дополнительные сведения см. в статье [Ручная подготовка базы данных-получателя для присоединения к группе доступности (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02166-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02166-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="02166-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02166-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="02166-123">Permissions</span></span>  
 <span data-ttu-id="02166-124">См. раздел [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="02166-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02166-125">Работа с мастером добавления реплики Azure (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="02166-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="02166-126">Мастер добавления реплики Azure можно запустить на странице [Выбор реплик](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="02166-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="02166-127">На эту страницу можно перейти двумя способами.</span><span class="sxs-lookup"><span data-stu-id="02166-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="02166-128">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="02166-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="02166-129">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="02166-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="02166-130">После того как был запущен мастер добавления реплики Azure, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="02166-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="02166-131">Сначала загрузите сертификат управления для подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="02166-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="02166-132">Нажмите кнопку **Загрузить** , чтобы открыть страницу входа.</span><span class="sxs-lookup"><span data-stu-id="02166-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="02166-133">На странице входа войдите в свою подписку Azure.</span><span class="sxs-lookup"><span data-stu-id="02166-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="02166-134">После входа мастер выполняет установку сертификата управления на ваш локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="02166-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="02166-135">Этот сертификат управления автоматически загружается при последующем использовании этого мастера.</span><span class="sxs-lookup"><span data-stu-id="02166-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="02166-136">Если было загружено несколько сертификатов управления, можно нажать кнопку **...** , чтобы выбрать нужный сертификат для использования.</span><span class="sxs-lookup"><span data-stu-id="02166-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="02166-137">Затем подключитесь к подписке, нажав кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="02166-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="02166-138">После подключения раскрывающиеся списки заполняются параметрами Azure, такими как **Виртуальная сеть** и **Подсеть виртуальной сети**.</span><span class="sxs-lookup"><span data-stu-id="02166-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="02166-139">Укажите параметры для виртуальной машины Azure, на которой будет размещаться новая вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="02166-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="02166-140">Образ —</span><span class="sxs-lookup"><span data-stu-id="02166-140">Image</span></span>  
     <span data-ttu-id="02166-141">Имя образа SQL Server, которое будет использоваться для виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="02166-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="02166-142">Размер виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="02166-142">VM Size</span></span>  
     <span data-ttu-id="02166-143">Размер виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="02166-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="02166-144">Имя виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="02166-144">VM Name</span></span>  
     <span data-ttu-id="02166-145">DNS-имя виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="02166-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="02166-146">Имя пользователя виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="02166-146">VM Username</span></span>  
     <span data-ttu-id="02166-147">Имя пользователя-администратора системы по умолчанию для виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="02166-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="02166-148">Пароль администратора виртуальной машины (и подтверждение пароля)</span><span class="sxs-lookup"><span data-stu-id="02166-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="02166-149">Пароль администратора системы по умолчанию для виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="02166-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="02166-150">Виртуальная сеть</span><span class="sxs-lookup"><span data-stu-id="02166-150">Virtual Network</span></span>  
     <span data-ttu-id="02166-151">Виртуальная сеть, в которой будет размещена виртуальная машина Azure</span><span class="sxs-lookup"><span data-stu-id="02166-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="02166-152">Подсеть виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="02166-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="02166-153">Подсеть виртуальной сети, в которой будет размещена виртуальная машина Azure</span><span class="sxs-lookup"><span data-stu-id="02166-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="02166-154">Домен</span><span class="sxs-lookup"><span data-stu-id="02166-154">Domain</span></span>  
     <span data-ttu-id="02166-155">Домен Active Directory (AD), к которому будет присоединена виртуальная машина Azure</span><span class="sxs-lookup"><span data-stu-id="02166-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="02166-156">Имя пользователя домена</span><span class="sxs-lookup"><span data-stu-id="02166-156">Domain Username</span></span>  
     <span data-ttu-id="02166-157">Имя пользователя AD, используемое для присоединения виртуальной машины Azure к домену</span><span class="sxs-lookup"><span data-stu-id="02166-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="02166-158">Пароль</span><span class="sxs-lookup"><span data-stu-id="02166-158">Password</span></span>  
     <span data-ttu-id="02166-159">Пароль, используемый для присоединения виртуальной машины Azure к домену</span><span class="sxs-lookup"><span data-stu-id="02166-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="02166-160">Нажмите кнопку **ОК** , чтобы зафиксировать ваши параметры, и выйдите из мастера добавления реплики Azure.</span><span class="sxs-lookup"><span data-stu-id="02166-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="02166-161">Продолжайте выполнять остальные шаги конфигурации на странице [Выбор реплик](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) так же, как и для любых новых реплик.</span><span class="sxs-lookup"><span data-stu-id="02166-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="02166-162">После завершения работы мастера групп доступности или мастера добавления реплики в группу доступности процесс настройки выполняет все операции в Azure, чтобы создать новую виртуальную машину, присоединить ее к домену AD, добавить в кластер Windows, включить высокий уровень доступности AlwaysOn и добавить новую реплику в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="02166-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="02166-163">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="02166-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="02166-164">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="02166-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="02166-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="02166-165">See Also</span></span>  
 <span data-ttu-id="02166-166">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="02166-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="02166-167">[Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="02166-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="02166-168">Добавление вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="02166-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
