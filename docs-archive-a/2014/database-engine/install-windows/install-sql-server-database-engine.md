---
title: Сведения о SQL Server ядро СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732905"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="50807-102">О компоненте SQL Server Database Engine</span><span class="sxs-lookup"><span data-stu-id="50807-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="50807-103">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] входит в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и является основной службой, предназначенной для хранения, обработки и обеспечения безопасности данных.</span><span class="sxs-lookup"><span data-stu-id="50807-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="50807-104">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] обеспечивает управляемый доступ к ресурсам и быструю обработку транзакций, что позволяет использовать его даже с самыми требовательными приложениями по обработке данных на предприятии.</span><span class="sxs-lookup"><span data-stu-id="50807-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="50807-105">поддерживает до 50 экземпляров компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="50807-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="50807-106">Сведения о создании типичной [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] установки см. в разделе [Install SQL Server 2014 мастера установки &#40;&#41;установки ](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="50807-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="50807-107">**Внимание!** Для локальной установки программа установки должна запускаться от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="50807-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="50807-108">При установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из удаленной общей папки необходимо использовать учетную запись домена с разрешениями на чтение и выполнение для удаленной общей папки.</span><span class="sxs-lookup"><span data-stu-id="50807-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="50807-109">Если на странице «Компоненты для установки» мастера установки **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выбран компонент** Database Engine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то будут установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="50807-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="50807-110">Репликация ― это необязательный компонент</span><span class="sxs-lookup"><span data-stu-id="50807-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="50807-111">Full-Text Search ― это необязательный компонент</span><span class="sxs-lookup"><span data-stu-id="50807-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="50807-112">Службы Data Quality Services являются необязательным компонентом.</span><span class="sxs-lookup"><span data-stu-id="50807-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50807-113">В этом выпуске установка флажка **Службы Data Quality Services** в программе установки не приводит к установке сервера служб Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="50807-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="50807-114">Для установки сервера DQS необходимо выполнить дополнительные шаги после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="50807-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="50807-115">Дополнительные сведения см. в разделе [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="50807-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="50807-116">Следующие дополнительные возможности могут применяться во многих типичных пользовательских сценариях.</span><span class="sxs-lookup"><span data-stu-id="50807-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="50807-117">Клиент Data Quality</span><span class="sxs-lookup"><span data-stu-id="50807-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="50807-118">Компоненты соединения</span><span class="sxs-lookup"><span data-stu-id="50807-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="50807-119">Модели программирования</span><span class="sxs-lookup"><span data-stu-id="50807-119">Programming models</span></span>  
  
-   <span data-ttu-id="50807-120">Средства управления</span><span class="sxs-lookup"><span data-stu-id="50807-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="50807-121">Компоненты документации</span><span class="sxs-lookup"><span data-stu-id="50807-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50807-122">По умолчанию при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] образцы баз данных и образцы кода не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="50807-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="50807-123">Дополнительные сведения об установке образцов баз данных и образцов кода см. на [веб-сайте CodePlex](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="50807-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50807-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="50807-124">See Also</span></span>  
 <span data-ttu-id="50807-125">[Функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="50807-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="50807-126">[Выпуски и компоненты SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="50807-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="50807-127">[Планирование установки SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="50807-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="50807-128">[Решения высокого уровня доступности (SQL Server)](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50807-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="50807-129">Обновление до SQL Server 2014 с помощью мастера установки &#40;установки&#41;</span><span class="sxs-lookup"><span data-stu-id="50807-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
